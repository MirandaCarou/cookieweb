<template>
    <v-footer class="colored" dark padless>
        <v-card flat tile class=" white--text py-5 px-5 text-center colored" width="100%">
            <v-row>
                <v-col cols="2" sm="4"> 
                    <v-car-text class="white--text pt-2 btn-cookie">
                        <v-btn icon @click="scroll('home')">
                            <v-icon color="#2699E6">mdi-cookie</v-icon>
                        </v-btn>
                    </v-car-text>
                </v-col>
                <v-col cols="4" sm="4"> 
                    <v-car-text class="pt-2 btn-social-medias">
                        <v-btn v-for="(icon, index) in icons" :key="icon" class="btn-social-medias mx-1 white--text" icon @click="navigateToUrl(index)">
                            <v-icon size="24px">{{ icon }}</v-icon>
                        </v-btn>
                    </v-car-text>
                </v-col>
                <v-col cols="6" sm="4">
                    <v-card-text class="created-by pt-2">
                        <v-btn class="mx-1 white--text" icon>
                            <v-icon color="#2699E6">mdi-heart</v-icon>
                        </v-btn>
                        Created by Miranda Carou
                    </v-card-text>
                </v-col>
            </v-row>
        </v-card>
    </v-footer>
</template>

<script>
    export default{
        name:'FooterBar',
        data: () => ({
            icons:[
                "mdi-linkedin", "mdi-github"
            ],
            urls: ['https://www.linkedin.com/in/mcarou','https://github.com/MirandaCarou', '(icon, index)'],
        }),
        methods: {
            navigateToUrl(index) {
                window.location.href = this.urls[index];
            },
            scroll(refName){
                const element = document.getElementById(refName);
                element.scrollIntoView({behavior: "smooth"});
            }
        },
    }
</script>

<style>
  body{
    background-color: #1e1e1e;
  }
  .colored{
    background-color: #111111;
  }
  
</style>