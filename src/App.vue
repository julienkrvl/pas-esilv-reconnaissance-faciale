<template>
       <v-app id="app"  standalone>
        <v-toolbar fixed >
            <v-toolbar-title class="red--text">ESILV : Projet PAS de reconnaissance faciale</v-toolbar-title>
        </v-toolbar>
        <main>
            <v-container fluid>
               <router-view></router-view>
            </v-container>
        </main>
         <v-footer class="pa-5">
    </v-footer>
    </v-app>
</template>

<script>
export default {

}
</script>
