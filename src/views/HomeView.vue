<template>
  <v-app id="home" >
    <NavBar />
    <v-container  fluid >
      <v-row>
        <v-col class="cookie-col" col="6">
          <v-img class="cookie-img" src="../../public/cookie.png" contain max-height="400">
          </v-img>
        </v-col>
        <v-col col="7" class="home-info">
          <h5 class="blue--text text-darken-4 top">Welcome to Cookie Controller</h5>
          <h1 class="white--text"> Add-on Open Source Project</h1>
          <p class="grey--text">
            A Chrome/Firefox Add-on for cookie control that allows the user to manage  <br/>
            the use of essential and non-essential cookies by websites. 
          </p>
          <v-btn href="https://github.com/MirandaCarou/Cookie-Blocker-Extension/blob/main/README.md" tile color="#2699E6" dark>About Project</v-btn>
        </v-col>
        <v-col cols="12" class="padd" id="about">
            <div class="first" >
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
                    <v-btn href="https://github.com/MirandaCarou/Cookie-Blocker-Extension" color="#2699E6" dark text>
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
                      <v-btn href="https://github.com/MirandaCarou/Cookie-Blocker-Extension/blob/main/CONTRIBUTING.md" color="#1e1e1e" dark text>
                        Know More
                        <v-icon right>mdi-arrow-right</v-icon>
                      </v-btn>
                  </div>
                </v-col>
              </v-row>
            </div>
            <div class="second">
              <div class="secondchild1" id="contact">
                <v-row class="contact-row">
                  <v-col class="cols-align" cols="7">
                    <h1 class="contact-title white--text">
                      Let´s work together on your next project
                    </h1>
                    <p class="contact-substitle grey--text">
                      If you have any feedback or any question, please reach out to me
                    </p>
                  </v-col>
                  <v-col class="cols-align btn" cols="5">
                    <v-btn @click="copyEmail()" tile color="#2699E6" dark class="mt-16">
                      Contact 
                      <v-icon color="#1e1e1e"> mdi-bell </v-icon>
                    </v-btn>
                    <div v-if="showModal" class="modal">
                      <p>{{ copyEmailMessage }}</p>
                    </div>
                  </v-col>
                </v-row>
              </div>
            </div> 
            <div class="third" cols="7">
              <v-row>
                <v-toolbar class="topTolbar" color="#111111" dark flat>
                  <div style="position: absolute; margin-left: auto; margin-right: auto; left: 0; right:0; text-align:center">
                    <v-btn text @click="scroll('home')">Home</v-btn>
                    <v-btn text @click="scroll('about')">About Add-on Project</v-btn>
                    <v-btn text @click="scroll('contact')">Contact</v-btn>
                  </div>
                </v-toolbar>
            </v-row>
            </div>
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
    data() {
        return {
          copyEmailMessage: '',
          email: 'mclainho19@esei.uvigo.es',
          showModal: false,
        };
    },
    components:{
      NavBar,
      FooterBar
    },
    methods: {
      scroll(refName){
        const element = document.getElementById(refName);
        element.scrollIntoView({behavior: "smooth"});
      },
      copyEmail() {
        navigator.clipboard.writeText(this.email).then(() => {
          this.copyEmailMessage = 'Contact email copied !';
          this.showModal = true;
          setTimeout(() => {
            this.showModal = false;
          }, 2000);
        }, (err) => {
          this.copyEmailMessage = 'Could not copy contact email: ' + err;
          this.showModal = true;
          setTimeout(() => {
            this.showModal = false;
          }, 2000);
        });
      },
    }
  }
</script>

<style scoped>

 body{
    background-color: #111111;
  }
  #home{
    background-color: #111111;
  }
  .topTolbar{
    text-align:center;
  }
  .cols-align{
    text-align: center;
  }
  .first{
    background-color: #111111;
    text-align:center;
  }
  .second{
    text-align: center;
  }
  .secondchild1{
    display: inline-flex;
    background-color: #1e1e1e;
    vertical-align: middle;
    text-align: left;
    align-items: center;
  }
  .child{
    display: inline-block;
    vertical-align: middle;
    text-align: left;
  }
  .bgColor1{
    background-color: #1e1e1e;
  }

  .bgColor2{
    background-color: #2699E6;
  }
  
  .btn {
    position: relative;
    flex-flow: wrap-reverse;
    display: flex;
    justify-content: center;
    vertical-align: middle;
    align-content: center;
  }
  .modal {
    height: 50px;
    width: 100px;
    background-color: #2699E6;
    color: white;
    font-size: 12px;
    font-style: inherit;
    position: absolute;
    top: 50%;
    left: 70%;
    transform: translate(0%, -50%);
    padding: 5px;
    border-radius: 2px;
    z-index: 1000;
  }
  @media (max-width: 1200px) {
    .home-info{
      display: flex;
      flex-direction: column;
      align-items: center;
      align-content: center;
      align-self: center;
    }
    .cookie-img{
      height: 300px;
      width: 900px;
    }
    .cookie-col{
      max-width: 50%;
    }
    #about{
      align-items: center;
      display: flex;
      flex-direction: column;
    }
    .first{
      width:60%;
    }
    .child1{
      padding: 20px;
      margin-bottom: 30px;
      margin-top: 50px;
    }
    .child2{
      padding: 20px;
      margin-bottom: 30px;
      margin-bottom: 90px;
    }
    .third{
      display: flex;
      width: 100%;
    }
    .contact-row{
      display: flex;
      flex-direction: column;
      align-items: center;
      height: 227px;
      width: 700px;
      padding: 30px;
    }
    .contact-title{
      font-size: 25px;
    }
    .second{
      margin-bottom: 50px;
    }
    .third{
      display: none;
    }
  }

  @media (max-width: 580px){
    .home-info h1{
      font-size: 20px;
    }
    .home-info p{
      font-size: 15px;
    }
    .first{
      width:90%;
    }
    .secondchild1{
      width: 50%;
    }
    .contact-row h1{
      font-size: 18px;
    }
    .cookie-col{
      max-width: 90%;
    }
    .contact-row p{
      font-size: 12px;
    }
  }
  @media (min-width: 1200px){
    .top{
      margin-top: 180px;
    }

    .topInverse{
      margin-top: -250px;
    }

    .topTolbar{
      margin-top:100px;
    }
  
    .first{
      width:100%;
      height: 610px;
      padding:2rem 2rem;

    }
    .second{
      width: 100%;
      height:400px;
      padding: 2rem 2rem;
    }

    .secondchild1{
      padding: 2rem 1rem;
      width: 80%;
      height: 80%;
    }

    .child{
      padding: 2rem 1rem;
      margin-right: 8px;
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
      padding-top: 150px;
    }

    .col-12.childcol{
      padding: 0 !important;
    }

    h1.number{
      font-size: 50px;
      font-weight: bold;
    }
    .cols-align .mt-16{
      margin-top: 0px !important;
      display: flex;
      vertical-align: middle;
    }
  }

</style>
