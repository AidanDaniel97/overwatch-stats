<template>
  <div id="app">
  <!-- Handlebars template -->


  <newUser v-on:firstLaunch="onFirstLaunch" v-if="firstLaunch"></newUser>



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
    onFirstLaunch: function(){
      this.firstLaunch = false;
      console.log("user set.")
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
