<template>
  <div id="app">
  <!-- Handlebars template -->
  <transition name="slide-fade">
    <newUser @playerSet="onPlayerSet"  v-transition stagger="100" v-if="firstLaunch"></newUser>
  </transition>

  <transition name="slide-fade">
    <miniStats v-if="!firstLaunch" enter-stagger="2000"></miniStats>
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
      firstLaunch: true,
		}
	},
  methods:{
    onPlayerSet (value) {
      console.log("Value recieved" , value) // someValue
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
