<template>
  <div id="app">
  <!-- Handlebars template -->
  <transition name="slide-fade-out">
    <newUser @playerSet="onPlayerSet" v-if="firstLaunch"></newUser>
  </transition>

  <transition name="slide-fade-in">
    <miniStats :userData='userData' v-if="!firstLaunch"></miniStats>
  </transition>


  <!--Load event listener-->
  <eventListener></eventListener>
  </div>
</template>

<script>
import newUser from './components/newUser.vue'
import miniStats from './components/miniStats.vue'
import eventListener from './components/eventListener.vue'
export default {
  name: 'app',
  components: {
     newUser,
     eventListener,
     miniStats
  },
	data(){
		return{
      firstLaunch: true,//set to true for production
      userData: null,
		}
	},
  methods:{
    onPlayerSet (user_data) {
      console.log("Value recieved" , user_data) // someValue
      this.userData = user_data;
      this.firstLaunch = false;
    }
  },
}




</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
