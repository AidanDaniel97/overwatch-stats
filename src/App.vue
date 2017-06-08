<template>
  <div id="app">
  <!-- Handlebars template -->
  <transition name="slide-fade-out">
    <newUser @playerSet="onPlayerSet" v-if="firstLaunch"></newUser>
  </transition>

  <transition name="slide-fade-in">
    <miniStats :userData='userData' @toggleFeed="onToggleFeed" v-if="!firstLaunch"></miniStats>
  </transition>

  <transition name="slide-in">
    <mainFeed v-if="toggleFeed"></mainFeed>
  </transition>


  <!--Load event listener-->
  <eventListener></eventListener>
  </div>
</template>

<script>
import newUser from './components/newUser.vue'
import miniStats from './components/miniStats.vue'
import eventListener from './components/eventListener.vue'
import mainFeed from './components/mainFeed.vue'


export default {
  name: 'app',
  components: {
     newUser,
     eventListener,
     miniStats,
     mainFeed
  },
	data(){
		return{
      firstLaunch: true,//set to true for production
      userData: null,
      toggleFeed: false
		}
	},
  methods:{
    onPlayerSet (user_data) {
      console.log("Value recieved" , user_data) // someValue
      this.userData = user_data;
      this.firstLaunch = false;
    },
    onToggleFeed(toggle){
      console.log("Feed toggled");
      if (this.toggleFeed){
        this.toggleFeed = false;
      }else{
        this.toggleFeed = true;
      }
    },
  }
}


</script>

<style>

</style>
