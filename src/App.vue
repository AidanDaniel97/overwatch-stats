<template>
  <div id="app">
  <!-- Handlebars template -->
  <transition name="slide-fade">
    <newUser @playerSet="onPlayerSet" v-on:firstLaunch="onFirstLaunch" v-if="firstLaunch"></newUser>
  </transition>


  <eventListener></eventListener>
  </div>
</template>

<script>
import newUser from './components/newUser.vue'
import eventListener from './components/eventListener.vue'
export default {
  name: 'app',
  components: {
     newUser,
     eventListener
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
