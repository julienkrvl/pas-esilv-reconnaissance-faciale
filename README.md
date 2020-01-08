# pas-esilv-reconnaissance-faciale
 
# Acknowledgement

First of all, we would like to thank our project tutor, Mrs. Nadia ABINA, who has provided us with her experience as well as a great deal of advice and knowledge throughout this semester, both from a research and technical point of view and in terms of presentations.

We also thank her for the follow-up of the missions entrusted to us and for her trust.

We thank Mrs Sophie DEPEYRE, PAS project manager, for her help and orchestration of the project throughout this semester.

**Table of contents**


I.        Introduction       

II.        State of the Art       

_A._        _History_       

_B._        _Detection methods and algorithms_        

III.        Features of facial recognition APIs: Amazon, Google, Microsoft and Facebook        

_A._        _APIs presentation_        

_B._        _Our Application_        

IV.        Conclusion        

V.        Resources        


# I.Introduction

&quot;Facial recognition is a biometric technology that identifies a person based on the characteristics of their face, including the distance between the different elements that make up the face.&quot;

The advantages of implementing such a biometric system :

- To facilitate the way of life
- Controlling the population
- Avoiding fraud
- Growth in the high-end multimedia and imaging field

There are 2 main techniques for recognizing individuals. There is the intrusive type of recognition : the physical integrity of the individual is engaged and the non-intrusive type of recognition where the physical integrity of the individual is not subjected.

In the graph below we find the different ways of identifying an individual by grouping the two types of recognition.




Leaving aside sophisticated identification techniques such as fingerprints, genetic fingerprints, examination of the iris, voice, capillary networks, etc., the most basic identification of an individual is based on the face: indeed, from early childhood, human beings are capable of identifying a person according to the face. It is therefore easy to understand that the methods of identification by facial recognition are the most traditional: in fact, for everyone, the face &quot;crystallizes the identity of the individual&quot;.

The recognition of a face is done by a third party or a video surveillance camera. In both cases the process is the same and, a positive recognition implies necessarily :

- A preliminary &quot;learning&quot; leading to a memorization of the subject&#39;s features,

- An analysis of the newly seen face, whose faciometric data are compared (by the brain or computer) with those stored in memory.

This can be summarized as follows:

# Learning - Memorization – Recognition


# II.State of the Art

 A._History_

First of all, biometrics makes it possible to identify a person not through possession or knowledge but on the basis of one or more physical or behavioural characteristics attached to the individual. Alphonse Bertillon, is the inventor of the first biometric system, later called the Bertillon system or Bertillonage in 1882. This system was based on a set of anthropometric measurements such as the length of the hand or the distance between the eyes. Unpractical and insufficiently reliable, the fingerprint was then imposed on the Bertillon system from the 1900s onwards. This identification system, also called &quot;Henry system&quot; in Anglo-Saxon countries for Edward Henry, is based on the uniqueness and permanence of certain skin figures (curls, arches, whirls).

One of the first attempts at face recognition was made by Takeo Kanade in 1973 during his doctoral thesis at Kyoto University. He also worked on John Daugmann&#39;s Iris in 1994. Some features such as the face are more studied than others because they are also used by humans to recognize each other in everyday life. Several researchers, in particular Anil Jain, also proposed in the early 2000s to use several biometric traits in order to build a multimodal system that would be more efficient than existing systems based on a single modality. Biometrics has now also been studied for about ten years in a video surveillance context. Most often, it is not a question of identifying individuals in the strict sense of the word, but of extracting several semantic traits (also called soft biometrics) such as height, gender, hair colour, etc. This information makes it possible to characterize a person, to find him/her on the basis of a visual testimony, or to follow him/her in a network of cameras. Initially confined to the criminal field, since 1951 biometrics has always been present in the cinema in numerous detective or science fiction films, with emblematic films such as Minory Report (2002). Currently biometrics is widely used in border controls. For example, since 2004, every visitor must &quot;give&quot; the fingerprints of his or her index fingers and a photograph of his or her face each time he or she enters the United States. The world&#39;s most ambitious digital identity programme, called Aadhaar (One Identity for All), was launched in India in 2010 and is based on the iris, fingerprint and face.

On June 7, 2011, Facebook launched a facial recognition service accessible to all.

Biometrics is even becoming a tool in everyday life to access resources in a reliable and user-friendly way. It is in this context that the iPhone X in 2017 will integrate a facial recognition module.

In France, the CNIL is trying to regulate its use and has published several recommendations and authorisations in recent years. It is also important to note that there are many IT tools available to reconcile, as far as possible, new technologies, security and privacy.



B._Detection methods and algorithms_

Face recognition generally consists of 4 steps: acquisition, pre-processing, extraction of descriptors, and finally classification for decision making (identity of the person).

 The acquisition provides information about the face of the person to be identified. Different sensors can be used for this purpose. They can be classified into two main categories: 2D sensors and 3D sensors. 2D sensors provide a photographic image of the person representing visual information. 3D sensors allow the acquisition of the three-dimensional shape of the face. Depending on the type of sensor used, the recognition approach is defined as 2D recognition or 3D recognition.

Then, a pre-processing step is often applied. The objective of this step is first to determine the presence or not of a face in the image, as well as its location (face detection). Once the face is detected, a normalization step is often applied. The face is geometrically normalized for alignment purposes. Illumination normalization can also be performed to compensate for lighting variations.

After the pre-processing step, the descriptor extraction step consists of extracting important information from the face image in order to provide a biometric signature, which is called a feature vector. The latter must imperatively satisfy two main properties: discrimination and robustness. A feature vector is discriminating if it takes significantly different values for the faces of two different people. As for robustness, it is the invariance of this vector to a certain number of variabilities (changes in expression, pose, lighting, etc.) of the same face. Finally, the classification is performed. It consists of two processes: learning and prediction. Learning is carried out on all the characteristic vectors of faces labelled according to their class (identity) in order to create a classifier. Prediction consists in assigning an unknown face to a class using the classifier constructed by the learning step. During this last step, we distinguish two tasks:

- Authenticate a person: Verify that a person is who they say they are.

- Identify a person: Find a person within a group of individuals, in a place, an image or a database.

All the steps of the detection are known, it is now sufficient to establish the Signature of the individual, in other words, we determine the uniqueness of a person and then identify him or her as shown in the summary diagram below.








**2D Recognition**



The recognition is then carried out by an algorithm that can rely on different elements, such as the shape of facial features like eyes and their spacing, mouth, face...

Two categories of algorithms are then distinguished:

 Creation of a geometric image of the user according to different parameters (size of facial elements, shape and distance between them).

 Digital encoding of the image, using Fourier algorithms, using eigenfaces to create weight vectors, or by averaging certain areas of the image.



**3D Recognition**

This method is considered as an improvement of 2D recognition:

It creates a 3D model from several photos taken successively or from a video...

Numerous algorithms based on one or more elements of the face (orientation of the nose, face...) to create the 3D model corresponding to the user&#39;s face as below.





**Limits and opportunities**

Facial recognition is a solution to improve security.

It is also an economic issue for product development and operation.

 But the issue is mainly about the evolution of the legal standard. It must guarantee the right balance between freedom and security in a cross-border context.

Facial recognition cannot do without human action, which alone bears the weight of responsibility for the choice of whether or not to intervene.























We will present more specifically the methods of recognition that have led to significant progress in this area. The first category includes identification methods using the whole face as the information to be processed by the system. These methods are often called global or holistic methods and generally aim to reduce the space of representation of the face. Some of the best known include the EigenFaces algorithm, FisherFaces, or Independent Component Analysis (ICA) and Evolution Pursuit. The second category includes identification methods based on particular facial characteristics (traits). These are called local methods. Among the most widespread methods belonging to this category are methods based on the LBP descriptor, methods based on Gabor wavelets, the EBGM method where a new facial descriptor is proposed. We find these ordered methods in the graph below :



We are now looking at the main methods used.




**Global Methods**

- **Principal Component Analysis**

PCA is a method of efficiently extracting information from an often complex data set by reducing the size of the space in which the data is observed and arranging it in a new space so that useful information is highlighted and secondary information is eliminated. The PCA algorithm suitable for face analysis and identification is known as EigenFaces and was developed by Turk and Pentland in 1991. It is divided into a learning phase and a classification phase. During the learning phase, a clean space is constructed from a learning base using the PCA method and then these same images are projected onto the resulting space. During the classification phase, a test face is projected in turn on this same space to be identified by comparing it to the projections of each of the faces of the learning base. This amounts to projecting the images on an orthogonal base of particular vectors that present the most independent characteristics of the faces (redundancy has therefore been eliminated) to highlight their differences.

- **Linear Discriminant Analysis**

The LDA algorithm for face analysis and identification is known as FisherFaces and was developed by Belhumeur at Yale University in the USA in 1997. Unlike the previous algorithm, which allows the extraction of characteristics specific to each image, this one allows a true class separation. Indeed, it uses a class label associated to each variable during the learning process. This technique is therefore based on supervised learning. It is the learning data that should allow us to perform a classification of these data and to find the class to which any new observation belongs. This requires to divide the learning base into c different classes beforehand. In other words, each person in this base is equivalent to a class and each of them is associated with at least two images. The objective of this algorithm is this time to maximize the ratio between inter-class variations (variations between images of different people) and intra-class variations (variations between images of the same person). Thus, as before, the FisherFace method consists in finding an adequate space on which the images of the learning base and the test base will be projected. The identification is carried out by comparing the projection of the test image with each of the projections of the images of the learning base.





**Local Methods**

Contrary to global methods, local methods allow to characterize locally a face by vectors of small dimensional features, which allows to get rid of all dimensionality problems encountered with holistic methods. On the other hand, they allow to represent a face thanks to multiple characteristics much more robust to certain variations such as variations in illumination for example. There are two strategies for this: methods based on local characteristics and methods based on the local appearance of the face. The first consists of first detecting facial features such as eyes, nose, mouth and then extracting characteristics. Generally, these correspond to the properties of the features themselves or to the relationships that may exist between them (angles, distances). The second consists in directly extracting local characteristics at the level of predefined regions of the face.





- **Gabor**

The extraction of the characteristics of a face by Gabor wavelets is the representation of both time and frequency of a signal which allows a better visualization of its content compared to its classical Fourier transform which only gives its frequency representation. This leads to a non-negligible counterpart since it limits the representation of the signal both in the time domain and in the frequency domain as illustrated by Heisenberg&#39;s uncertainty principle. This representation makes it possible to detect particular features in an image while minimizing the effects of variations. Consequently, wavelet transformation is very efficient for the extraction of facial features. In particular, Gabor filters have properties that are interesting in the biological and mathematical sense of the term.

- **Convolutional neural networks**

These networks are used for any use around the image or video of which facial recognition or image classification is a part. Snapchat and many mobile applications have used the breakthrough of learning and CNNs to increase their &quot;filtering&quot; capabilities. The name convolutional network refers to a mathematical term: the convolution product.In simple terms, the idea is that a filter is applied to the input image, the filter settings will be learned as it is learned.

A learned filter will, for example, allow us to detect angles in an image if the angles are used to best classify the image. The image is first decomposed into the 3 channels (R, G, B) pixel by pixel, thus obtaining 3 matrices of size n x n (n is the number of pixels). The network can learn step by step to recognize the characteristic elements of an image. To recognize a face for example: it will first learn to recognize eyelids, pupils, to be able to identify eyes. Once an element is learned at one place in the image, the network will be able to recognize it anywhere else in the image.

- **So-called recurrent neural networks**

Recurrent neural networks are at the heart of many substantial improvements in areas as diverse as speech recognition, automatic music composition, sentiment analysis, DNA sequence analysis, and machine translation.

The main difference with other neural networks is that they take into account the successive sequencing of data, often their sequencing over time. For example in the case of the analysis of a series of sensor measurements (time series) the network will still have in memory all or part of the previous observations.

Instead of taking into account the input data separately (like a CNN analyzes frame by frame) the recurrent network takes into account the past input data.

Some architectures, known as bidirectional, can also take into account future data.

**Hybrid Methods**

The human visual system processes information in both local and global forms, and face recognition requires a combination of both types of information. Unfortunately, until now, we do not know how all this information is processed in our brain. Nevertheless, several methods of automatic face recognition seek to model an identification system that combines information from these two types of characteristics, the so-called hybrid methods. The goal of these approaches is therefore to find out which characteristics of a face are useful for recognition and how to combine them in order to facilitate the identification of a person. These characteristics have different and complementary properties: while local characteristics are very sensitive to noise, global characteristics are not. On the other hand, the global characteristics are very sensitive to installation, unlike the local characteristics. This clearly shows why this type of method is so popular.




# III.Features of facial recognition APIs: Amazon, Google, Microsoft and Facebook

A._ __APIs presentation_

**AMAZON REKOGNITION**

Rekognition Image is an image recognition service based on deep learning.

**Features**

- **--** Object and Scene Detection
- **--** Facial Analysis
- **--** Facial Comparison
- **--** Inappropriate Image Detection
- **--** Celebrity Recognition
- **--** Text In Picture


**Google vision  **

The Google Cloud Vision API has powerful learning machine models pre-trained through the REST and RPC APIs.

**Features**

- **--** Detecting objects
- **--** Activate product search with Vision
- **--** Detecting printed and handwritten text
- **--** Detecting faces
- **--** Identify popular locations and product logos
- **--** Detect Web pages and entities
- **--** Moderate content



**Microsoft Visage**

The Azure Cognitive Services Face API provides algorithms that are used to detect, recognize and analyze human faces in images.

**Features**

- **--** Detecting Faces
- **--** Detecting groups of people
- **--** Facial Verification



**Facebook DeepFace**

Deep learning facial recognition that identifies human faces in digital images. It uses a nine-layer neural network with more than 120 million connection weights and has been trained on four million images uploaded by Facebook users.

**Features**

- **--**** Detecting Faces**
- **--**** Detecting groups of people**
- **--**** Facial Verification**


## It should be noted that these different APIs all have a common service: Face recognition.

## Then some groups propose services and prediction methods that can vary according to the capacity of the company.

## Indeed, companies that offer prediction methods with Deep Learning have much richer databases than those that offer Learning machines. Deep Learning requires a large amount of data. We can see that Facebook offers a method of detection via Deep Learning, in fact, Facebook has a large amount of photos that feed the databases through the social network Facebook. This social network now has 2.45 billion active users. This is not the case with Microsoft or even Google.

## The enrichment of databases is the main barrier to entry for large groups that want to dominate the facial recognition market and offer increasingly accurate results.

B._Our Application_

# Github Link : [https://github.com/julienkrvl/pas-esilv-reconnaissance-faciale](https://github.com/julienkrvl/pas-esilv-reconnaissance-faciale)

There are 6 elements that are essential to the functioning of this application, if even one of these elements were to be out of order, the application would not be able to work. For this, AWS servers must be very robust and fast to provide continuity of service to these clients.

**1) Elements**

**A Web server (Back-end) :**

A web server is a computer server that responds to requests from the World Wide Web, mainly using the http or https protocol. The term designates both the software part and the hardware part on which it runs to broadcast content on a public (Internet) or private (intranet) network.

A computer server can be used both to serve web resources and to run other related services such as sending e-mails, streaming, storing data via databases, transferring files via FTP, etc. in parallel.

Here, our web server mainly uses the http / https protocol (port 80 / 443) to receive, answer and send requests through the Internet.

To ensure this functionality our server uses the http server node.js (with the Framework express.js) in tandem with another http server, which we use here to serve the client&#39;s index.html file (see &quot;A client (Front-End)&quot; below) and as a reverse proxy.

**What is a reverse proxy ?**

A reverse proxy is a type of server, usually placed in front of web servers. Unlike a proxy server that allows a user to access the Internet, a reverse proxy allows an Internet user to access internal servers. One of the common applications of reverse proxy is load-balancing.

**Why use a reverse proxy?**

We use here the Ngnix server as a reverse proxy to avoid starting our node.js application on port 80, and to allow us to launch several applications on this server.

Here, our http server / application node.js listens on port 8081, the reverse proxy (which listens on port 80) will redirect the request automatically on port 8081 according to several predefined parameters in the server configuration files (etc/nginx/conf.d).

Here it will be redirected if the sub-domain is &quot;api.mydomainname.tld&quot;.



**A database:**

A database allows to store and retrieve all raw data or information related to a theme or activity; these can be of different natures and more or less related to each other. Indeed, their data can be highly structured (relational database for example), or hosted in the form of unstructured raw data (NoSQL Redis database for example) which, in this case, will then be browsed in an organized manner at the time of reading via specific engines (such as Elasticsearch). A database can be located in the same place and on the same computer medium, or distributed on several machines in several locations (NoSQL database for example).

Here we have set up a NOSQL database in MongoDB, this database can be used to store any data but we have not had the opportunity to use it in our application.

On the other hand, we could use it if we have to make the application evolve.



**A front-end client:**

In a computer network, a client is the software that sends requests to a server. It can be a piece of software manipulated by a person, a web page or even a bot. The computer from which the requests are sent, the software that contains the instructions for making the requests, and the person who operates the requests are all called clients.

The client computer is usually an ordinary personal computer, equipped with software related to the different types of requests that are going to be sent, such as a web browser, client software for the World Wide Web.

Here our client communicates to our web server directly via the web browser (HTML, CSS, JS etc.).

To create this client we used the JavaScript Framework Vue.js.

Vue.js is a progressive framework for building user interfaces. Unlike other monolithic frameworks (e.g. simple HTML / CSS page), Vue.js is designed from the start to be dynamic (JS).

**The AWS Rekognition :**

**What is an API (Application Programming Interface) :**

In computer science, an application programming interface or API (often referred to as an API for application programming interface) is a standardized set of classes, methods, functions and constants that serves as a front end through which one piece of software provides services to other pieces of software. It is provided by a software library or web service, usually accompanied by a description that specifies how consumer programs can use the functionality of the vendor program.

Here the Amazon API is used to communicate with the Amazon S3 storage service and the image recognition service.



**AWS S3 (Bucket) :**

Amazon Simple Storage Service (Amazon S3) is an object storage service.

For our application we use an S3 bucket to store our images, because the Rekognizion AWS API can only analyze an image that is already in an Amazon S3 bucket.

**The image recognition algorithm of AWS :**

The AWS image recognition algorithm is based on deep learning.

This algorithm makes it easy to add image and video analysis using deep learning technology, which does not require any machine learning expertise. With Amazon Rekognition, we can identify objects, people, text, scenes and activities in images and videos, as well as detect inappropriate content. Amazon Rekognition also provides facial analysis and facial search capabilities that can be used to detect, analyze, and compare faces in different use cases.

1) **How the application works**

First, the user makes his first GET request to our server via the app.my domain name. tld to get the front-end client in view.js which compiled for production (build) is an index.html file.

Once obtained the client is displayed on the screen of his browser and he can choose a picture to analyze (in his files or using his webcam directly) and then send it to our server by filling in the form.

Once the POST type request validated via the domain name api.monnomdedomaine.tld and the image uploaded on the server, we will send it to our Amazon S3 bucket saving its id / name to find it later.

The image has been saved on the server, so we will now send a call to the AWS Rekognition API to analyze the image using its id / name on the Amazon S3 bucket.

When we get the answer of this call, we answer to the client the information received. The user can now see the result of the analysis of this image directly through the client in his web browser.

 2) **Architecture**






# IV.Conclusion

Technically, facial recognition is an easy to use, inexpensive technique that can be applied at a distance from the subject.

It is the simplest and least restrictive technique, but it still has a long way to go.

Due to its easy-to-use nature, facial recognition will remain a powerful tool despite the existence of other competing biometric methods.

Despite all the progress that has been made, the problems of posing, lighting and identification in variable environments remain &quot;challenges&quot; that will require the efforts of researchers.

The ability to enrich databases to offer Deep Learning prediction methods is also a Challenge that only a few groups and countries are able to offer.

To overcome these challenges, it is important for anthropologists to participate more actively in the development of such systems.

        In terms of the research and development of this project, a four-point assessment is proposed:

- Opportunities: Developing the scientific and intellectual approaches to the topic
- REST application Not feasible: financial means not brought to the project - no API keys available.
- Technical comparison of the models Not feasible: Large Tech companies do not disclose the models used to perform their respective facial recognition.
- Only the functionality aspect is comparable.















1.
# V.Resources

-
# Quand la machine apprend (Yann Lecun, 2019)
-
# [https://fr.wikipedia.org/wiki/Syst%C3%A8me\_de\_reconnaissance\_faciale](https://fr.wikipedia.org/wiki/Syst%C3%A8me_de_reconnaissance_faciale)
-
# [https://www.scienceabc.com/innovation/facial-recognition-works.html](https://www.scienceabc.com/innovation/facial-recognition-works.html)
-
# [https://www.theguardian.com/technology/2019/jul/29/what-is-facial-recognition-and-how-sinister-is-it](https://www.theguardian.com/technology/2019/jul/29/what-is-facial-recognition-and-how-sinister-is-it)
-
# [http://scholarworks.sjsu.edu/cgi/viewcontent.cgi?article=8182&amp;context=etd\_theses](http://scholarworks.sjsu.edu/cgi/viewcontent.cgi?article=8182&amp;context=etd_theses)
-
# [https://core.ac.uk/download/pdf/61804826.pdf](https://core.ac.uk/download/pdf/61804826.pdf)
-
# [https://www.francebleu.fr/infos/transports/des-controles-a-reconnaissance-faciale-aux-aeroports-d-orly-et-roissy-1530879629](https://www.francebleu.fr/infos/transports/des-controles-a-reconnaissance-faciale-aux-aeroports-d-orly-et-roissy-1530879629)
-
# [https://prezi.com/96zbjndtvjwa/reconnaissance-faciale/](https://prezi.com/96zbjndtvjwa/reconnaissance-faciale/)
-
# [https://fr.slideshare.net/bgdu49xxx/reconnaissance-faciale](https://fr.slideshare.net/bgdu49xxx/reconnaissance-faciale)
-
# [https://towardsdatascience.com/an-intro-to-deep-learning-for-face-recognition-aa8dfbbc51fb](https://towardsdatascience.com/an-intro-to-deep-learning-for-face-recognition-aa8dfbbc51fb)
-
# [https://www.media.mit.edu/articles/face-recognition-researcher-fights-amazon-over-biased-ai/](https://www.media.mit.edu/articles/face-recognition-researcher-fights-amazon-over-biased-ai/)
-
# [http://www.theses.fr/fr/?q=reconnaissance+faciale](http://www.theses.fr/fr/?q=reconnaissance+faciale)
-
# [https://azure.microsoft.com/fr-fr/services/cognitive-services/](https://azure.microsoft.com/fr-fr/services/cognitive-services/)
-
# [https://aws.amazon.com/fr/rekognition/](https://aws.amazon.com/fr/rekognition/)
-
# [https://www.huffingtonpost.fr/2014/03/20/deepface-reconnaissance-faciale-facebook\_n\_5000872.html](https://www.huffingtonpost.fr/2014/03/20/deepface-reconnaissance-faciale-facebook_n_5000872.html)
-
# [https://cloud.google.com/vision/?hl=fr](https://cloud.google.com/vision/?hl=fr)
-
# [https://github.com/julienkrvl/pas-esilv-reconnaissance-faciale](https://github.com/julienkrvl/pas-esilv-reconnaissance-faciale)
-
# [https://trello.com/b/bGp1BRJY/projet-pas](https://trello.com/b/bGp1BRJY/projet-pas)
