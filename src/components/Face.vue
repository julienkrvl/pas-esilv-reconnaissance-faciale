<template>
<v-layout row wrap>
      <v-flex xs12 sm12 md12 lg12 xl12>
           <v-card>
          <video id="video" width="100%" height="50%" autoplay></video>
          <canvas id="canvas" width="600" height="480" style="display: none;"></canvas>
           </v-card>
          <v-btn @click.native="process" block >
              <v-icon left>camera_alt</v-icon> Analyser</v-btn>
      </v-flex>
      <v-flex xs12 sm12 md12 lg12 xl12>
        <p>Service : AWS Rekognition</p>
        <h2 class="blue--text text-xs-center">Resultats :</h2>
        <div class="text-xs-center" v-show="loader1">
          <v-progress-circular indeterminate v-bind:size="100" v-bind:width="3" class="amber--text"></v-progress-circular>
        </div>
        <div v-show="result1" class="text-xs-center">
          <p>
            La personne est <span v-if="gender === 'Male'">un homme</span><span v-if="gender === 'Female'">une femme</span>, il a environ entre {{ageLow}} et {{ageHigh}} ans.
            {{smile}}, ses yeux sont {{eyesBool}} et sa bouche est {{mouthBool}}.
          </p>
          <p>
            {{mustacheBool}} moustache et {{beardBool}} barbe.
          </p>
          <p>
            {{eyeglassesBool}} lunettes et {{sunglassesBool}} lunettes de soleil
          </p>
          <p>
            Sa principale émotion est {{emotion}}
          </p>
        </div>
      </v-flex>
      <v-flex xs12 sm12 md12 lg12 xl12>
          <h2 class="blue--text text-xs-center">Resultats détaillés :</h2>
             <div class="text-xs-center" v-show="loader1">
              <v-progress-circular indeterminate v-bind:size="100" v-bind:width="3" class="amber--text"></v-progress-circular>
              </div>
                <div v-show="result1" class="text-xs-center">

              <p>Genre : <span class="green--text">  {{gender}} </span> <span class="green--text">  {{genderConfidence}} %</span> </p>
              <p>Age (intervalle) : <span class="green--text">  {{ageLow}}  -</span> <span class="green--text">  {{ageHigh}} ans</span> </p>
              <p>{{smile}} : <span class="green--text"> {{smileConfidence}} %</span> </p>
              <p>Les yeux sont {{eyesBool}} : <span class="green--text">  {{eyesOpen}} %</span> </p>
              <p>La bouche est {{mouthBool}} : <span class="green--text">  {{mouthOpen}} %</span> </p>
              <p>{{mustacheBool}} mustache : <span class="green--text">  {{mustache}} %</span> </p>
              <p>{{beardBool}} barbe : <span class="green--text">  {{beard}} %</span> </p>
              <p>Emotion principale : <span class="green--text"> {{emotion}} {{emotionConfidence}} %</span> </p>
              <p>{{eyeglassesBool}} lunettes : <span class="green--text">  {{eyeglasses}} %</span> </p>
              <p>{{sunglassesBool}} lunettes de soleil : <span class="green--text">  {{sunglasses}} %</span> </p>
               <h4 class="pink--text">Confiance : {{ confidence2 }} %</h4>
          </div>
      </v-flex>
  </v-layout>
</template>

<script>
import $ from "jquery";
import axios from 'axios';
const AWS = require('aws-sdk');
AWS.config.update({region:'eu-west-1',accessKeyId: process.env.AWSKEYID,secretAccessKey: process.env.AWSKEYSECRET});
const rekognition = new AWS.Rekognition({apiVersion: '2016-06-27'});
const s3bucket = new AWS.S3({params: {Bucket: 'reconnaissance-faciale'}});
export default {
  data(){
      return{
        loader1: false,
        result1: false,
        gender: null,
        genderConfidence: null,
        emotion: null,
        emotionConfidence: null,
        ageHigh: null,
        ageLow:null,
        smile:null,
        smileConfidence: null,
        eyesOpen:null,
        eyesBool:null,
        mouthOpen:null,
        mouthBool:null,
        mustache:null,
        mustacheBool:null,
        beard:null,
        beardBool:null,
        eyeglasses:null,
        eyeglassesBool:null,
        sunglasses: null,
        sunglassesBool: null,
        confidence2:null,
      }
  },
    methods: {
      process() {
          const canvas = document.getElementById('canvas');
          const context = canvas.getContext('2d');
          const vm = this;
          this.result1 = false;
          this.loader1 = true;
          context.drawImage(video, 0, 0, 640, 480);
          const img = canvas.toDataURL('image/jpeg');
          const base64data = new Buffer(img.replace(/^data:image\/\w+;base64,/, ""),'base64');

  s3bucket.createBucket(function () {
  var params = {
      Key: 'img.jpg',
      Body: base64data
  };
  s3bucket.upload(params, function (err, data) {
      if (err) {
          console.log(err);
      } else {
  rekognition.detectFaces( {
      Image: {
          S3Object: {
              Bucket: "reconnaissance-faciale",
              Name:"img.jpg"
              }
          },
      Attributes: [
              "ALL"
              ]
}, function(error, response) {
  if (error){
       console.log(error);
  } else {
      const res = response.FaceDetails[0];
      vm.gender = res.Gender.Value;
      vm.genderConfidence = res.Gender.Confidence.toFixed(1);
      vm.ageHigh = res.AgeRange.High;
      vm.ageLow = res.AgeRange.Low;
      vm.smile = res.Smile.Value == true ? 'La personne sourit' : 'La personne ne sourit pas';
      vm.smileConfidence = res.Smile.Confidence.toFixed(1);
      vm.eyesOpen = res.EyesOpen.Confidence.toFixed(1);
      vm.eyesBool = res.EyesOpen.Value == true ? 'ouvert' : 'fermé';
      vm.mouthOpen = res.MouthOpen.Confidence.toFixed(1);
      vm.mouthBool = res.MouthOpen.Value == true ? 'ouverte' : 'fermée';
      vm.mustache = res.Mustache.Confidence.toFixed(1);
      vm.mustacheBool = res.Mustache.Value == true ? 'La personne a de la' : 'La personne n\'a pas de';
      vm.beard = res.Beard.Confidence.toFixed(1);
      vm.beardBool = res.Beard.Value  == true ? 'La personne a de la' : 'La personne n\'a pas de';
      vm.eyeglasses = res.Eyeglasses.Confidence.toFixed(1);
      vm.eyeglassesBool = res.Eyeglasses.Value == true ? 'La personne a des' : 'La personne n\'a pas de';
      vm.sunglasses = res.Sunglasses.Confidence.toFixed(1);
      vm.sunglassesBool = res.Sunglasses.Value == true ? 'La personne a des' : 'La personne n\'a pas de';
      vm.confidence2 = res.Confidence.toFixed(3);
      vm.emotion = res.Emotions[0].Type
      vm.emotionConfidence = res.Emotions[0].Confidence.toFixed(1)
      res.Emotions.forEach(function(element) {
          if (vm.emotionConfidence < element.Confidence) {
            vm.emotionConfidence = element.Confidence.toFixed(1)
            vm.emotion = element.Type
          }
      });
      vm.loader1 = false;
      vm.result1 = true;
      console.log(res)
      console.log("OK")
        }
       });
      }
     });
    })
   }
  }
}
 $(function() {
        const video = document.getElementById('video');
        if (navigator.mediaDevices && navigator.mediaDevices.getUserMedia) {
           navigator.mediaDevices.getUserMedia({
               video: true
           }).then(stream => {
               video.srcObject=stream;
                video.play();
            });
          }
        });

</script>


<style>
p {
    font-size: 18px
}
</style>
