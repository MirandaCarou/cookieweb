<template>
    <v-app-bar app color="#111111" dark flat >
        <v-btn icon @click="scroll('home')">
            <v-icon color="#2699E6">
               cookie 
            </v-icon>
        </v-btn>
        <v-spacer></v-spacer>
        <v-btn class="btn-navbar" text @click="scroll('home')">Home</v-btn>
        <v-btn class="btn-navbar" text @click="scroll('about')">About Add-on Project</v-btn>
        <v-btn class="btn-navbar" text @click="scroll('contact')">Contact</v-btn>
    </v-app-bar>
</template>

<script>
    export default{
        name: 'NavBar',
        methods: {
            scroll(refName){
                const element = document.getElementById(refName);
                element.scrollIntoView({behavior: "smooth"});
            }
        }
    }
</script>

<style>
  body{
    background-color: #111111;
  }
  @media (max-width: 580px){
    .btn-navbar{
        font-size: 10px !important;
        padding-right: 5px !important;
        padding-left: 5px !important;
    }
  }
</style>