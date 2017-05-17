<template>
  <div id="app">
  <!-- Handlebars template -->


  <newUser v-if="firstLaunch"></newUser>






  </div>
</template>

<script>
import newUser from './components/newUser.vue'
export default {
  name: 'app',
  components: {
     newUser
  },
	data(){
		return{
      firstLaunch: true,
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
  margin-top: 60px;
}
</style>
