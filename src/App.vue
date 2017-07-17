<template>
  <div id="app">
  <!-- Handlebars template -->

  <transition name="slide-side-out">
    <guidesWindow :currentGuide='currentGuide'  v-if="toggleGuides"></guidesWindow>
  </transition>


  <transition name="slide-fade-out">
    <newUser @playerSet="onPlayerSet" v-if="userObject.firstLaunch"></newUser>
  </transition>

  <transition name="slide-fade-in">
    <miniStats :userData='userObject' @toggleFeed="onToggleFeed" v-if="!userObject.firstLaunch"></miniStats>
  </transition>

  <transition name="slide-in">
    <mainFeed :userData='userObject, currentHero'  @toggleGuides="onToggleGuides" v-if="toggleFeed"></mainFeed>
  </transition>


  <!--Load event listener-->
  <eventListener @gameEvent="onGameEvent"></eventListener>
  </div>
</template>

<script>
import newUser from './components/newUser.vue'
import miniStats from './components/miniStats.vue'
import eventListener from './components/eventListener.vue'
import mainFeed from './components/mainFeed.vue'
import guidesWindow from './components/guidesWindow.vue'


export default {
  name: 'app',
  components: {
     newUser,
     eventListener,
     miniStats,
     mainFeed,
     guidesWindow
  },
	data(){
		return{
      userData: null,
      toggleFeed: false,
      toggleGuides: false,
      userObject: {
        firstLaunch: true,
        userData: null
      },
      currentGuide: null,
      currentHero: null,
		}
	},
  created: function () {
    console.log("Checking first launch: ", JSON.parse(localStorage.getItem("userData")))
    if (!JSON.parse(localStorage.getItem("userObject"))){
      this.userObject.firstLaunch = true;
    }else{
      this.userObject.firstLaunch = false;
      //Set userObject
      this.userObject = JSON.parse(localStorage.getItem("userObject"))
    }

    navigator.__defineGetter__('userAgent', function(){
        return 'Mozilla/5.0 (iPhone; CPU iPhone OS 10_2_1 like Mac OS X) AppleWebKit/602.4.6 (KHTML, like Gecko) Version/10.0 Mobile/14D27 Safari/602.1' // customized user agent
        console.log("user agent set");
    });

  },
  methods:{
    onPlayerSet (user_data) {
      console.log("Player set: " , user_data) // someValue
      this.userObject.userData = user_data;
      this.userObject.firstLaunch = false;
      localStorage.setItem("userObject", JSON.stringify(this.userObject))
    },
    onToggleFeed(toggle){
      console.log("Feed toggled");
      if (this.toggleFeed){
        this.toggleFeed = false;
      }else{
        this.toggleFeed = true;
      }
    },
    onToggleGuides(guide){
      console.log("Guides toggled " , guide);
      this.currentGuide = guide;
      if (this.toggleGuides){
        this.toggleGuides = false;
      }else{
        this.toggleGuides = true;
      }
    },
    onGameEvent(eventRecieved){
      console.log(eventRecieved.info)
      console.log("Event recieved from listner component: " , eventRecieved);
      if(eventRecieved.info){
        console.log("player number: " , )
        switch(eventRecieved.info.player.heroSelected) {
        case '41':
            this.currentHero = "genji"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '66':
            this.currentHero = "mcree"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '8':
            this.currentHero = "pharah"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '2':
            this.currentHero = "reaper"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '110':
            this.currentHero = "soldier76"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '46':
            this.currentHero = "sombra"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '3':
            this.currentHero = "tracer"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '21':
            this.currentHero = "bastion"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '5':
            this.currentHero = "hanzo"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '101':
            this.currentHero = "junkrat"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '221':
            this.currentHero = "mei"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '6':
            this.currentHero = "torbjorn"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '10':
            this.currentHero = "widowmaker"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '122':
            this.currentHero = "dva"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '62':
            this.currentHero = "orisa"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '7':
            this.currentHero = "reinhardt"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '64':
            this.currentHero = "roadhog"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '9':
            this.currentHero = "winston"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '104':
            this.currentHero = "zarya"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '59':
            this.currentHero = "ana"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '121':
            this.currentHero = "lucio"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '4':
            this.currentHero = "mercy"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '22':
            this.currentHero = "symmetra"
            console.log("Hero selected: " , this.currentHero);
            break;
        case '32':
            this.currentHero = "zenyatta"
            console.log("Hero selected: " , this.currentHero);
            break;
      }
    }
  },
}
}


</script>

<style>

</style>
