<template>
  <v-app id="home" :style="{background: $vuetify.theme.themes.dark.background}">
    <NavBar/>
    <v-container fluid>
      <v-row>
        <v-col col="6">
          <v-img src="../../public/cookie.png" contain max-height="400">
          </v-img>
        </v-col>
        <v-col col="6">
          <h5 class="blue--text text-darken-4 top">Welcome to Cookie Controller</h5>
          <h1 class="white--text"> Add-on Open Source Project</h1>
          <p class="grey--text">
            A Chrome/Firefox Add-on for cookie control that allows the user to manage  <br/>
            the use of essential and non-essential cookies by websites. 
          </p>
          <v-btn tile color="#2699E6" dark>About Porject</v-btn>
        </v-col>
        <v-col cols="12" class="padd">
            <div class="first" id="about">
              <v-row>
                <v-col cols="12">
                  <div class="child1 bgColor1">
                    <v-icon color="#2699E6" x-large class="ml-3"> 
                      cookie
                    </v-icon>
                    <h3 class="white--text ml-3 mt-4">Cookie Controller  Project</h3>
                    <p class="grey--text ml-3 mt-6">
                      This is an open source project that provides a framework structure that allows future contributors to add new CMPs and extend the Chrome plug-in control network.
                      Initially it is only operational for pages managed by the following CMPs:
                      Complianz, CookieNotice, CookieYes, Didomi, OneTrust and Osano. 
                    </p>
                    <v-btn color="#2699E6" dark text>
                      Know More
                      <v-icon right>mdi-arrow-right</v-icon>
                    </v-btn>
                  </div>
                  <div class="child2 bgColor2">
                      <v-icon color="#1e1e1e" x-large class="ml-3" dark>
                        mdi-account-group
                      </v-icon>
                      <h3 class="black--text ml-3 mt-4">Contributing</h3>
                      <p class="white--text ml-3 mt-6">
                        First off, thanks for taking the time to think about contribute! 
                        All types of contributions are encouraged and valued ❤️
                        See contributing.md for ways to get started and please adhere to this project's code of conduct.
                        Anyway, there are a lot of ways to support the project and show your appreciation.
                      </p>
                      <v-btn color="#1e1e1e" dark text>
                        Know More
                        <v-icon right>mdi-arrow-right</v-icon>
                      </v-btn>
                  </div>
                </v-col>
              </v-row>
            </div>
        </v-col>
        <v-col cols="12" class="padd topInverse">
          <div class="second">
            <div class="secondchild1" id="contact">
              <v-row>
                <v-col class="cols-align" cols="7">
                  <h1 class="white--text">
                    Let´s work together on your next project
                  </h1>
                  <p class="grey--text">
                    If you have any feedback or any question, please reach out to me
                  </p>
                </v-col>
                <v-col class="cols-align" cols="5">
                  <v-btn tile color="#2699E6" dark class="mt-16">
                    Contact 
                    <v-icon color="#1e1e1e"> mdi-bell </v-icon>
                  </v-btn>
                </v-col>
              </v-row>
            </div>
          </div>
          <v-toolbar class="topTolbar" color="#111111" dark flat>
            <div style="position: absolute; margin-left: auto; margin-right: auto; left: 0; right:0; text-align:center">
              <v-btn text>Home</v-btn>
              <v-btn text>About Add-on Project</v-btn>
              <v-btn text>Contact</v-btn>
            </div>
          </v-toolbar>
        </v-col>
      </v-row>
    </v-container>
    <FooterBar/>
  </v-app>
</template>

<script>
  import NavBar from '../components/NavBar.vue'
  import FooterBar from '../components/Footer.vue'

  export default{
    name: 'HomeView',

    components:{
      NavBar,
      FooterBar
    }
  }
</script>

<style scoped>
  .top{
    margin-top: 180px;
  }

  .topInverse{
    margin-top: -250px;
  }

  .topTolbar{
    margin-top:100px;
    text-align:center;
  }
  .cols-align{
    text-align: center;
  }
  .first{
    width:100%;
    height: 610px;
    background-color: #111111;
    text-align:center;
    padding:2rem 2rem;

  }

  .second{
    width: 100%;
    height:400px;
    background: #111111;
    text-align: center;
    padding: 2rem 2rem;
  }

  .secondchild1{
    display: inline-flex;
    background-color: #1e1e1e;
    padding: 2rem 1rem;
    vertical-align: middle;
    text-align: left;
    margin-top: 150px;
    width: 80%;
    align-items: center;
    height: 80%;
  }

  .child{
    display: inline-block;
    padding: 2rem 1rem;
    vertical-align: middle;
    text-align: left;
    margin-right: 8px;
  }

  .bgColor1{
    background-color: #1e1e1e;
  }

  .bgColor2{
    background-color: #2699E6;
  }

  .child1{
    display: inline-block;
    padding: 2rem 1rem;
    vertical-align: middle;
    margin-right: 5px;
    width: 440px;
  }

  .child2{
    display: inline-block;
    padding: 2rem 1rem;
    vertical-align: middle;
    margin-right: 5px;
    width: 440px;
  }

  .mRight{
    margin-right: 8px;
  }

  .mButton{
    margin-bottom: 8px;
  }

  .padding{
    padding: 8px 0px;
  }

  .col-12.padd{
    padding: 12px 0 !important;
  }

  .col-12.childcol{
    padding: 0 !important;
  }

  h1.number{
    font-size: 50px;
    font-weight: bold;
  }
</style>