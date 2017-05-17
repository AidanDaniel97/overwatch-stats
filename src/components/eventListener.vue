<template>
	<div class="eventListener">
	</div>
</template>

<script>
	export default{
		name: "eventListener",
		data(){
			return{
				message: "Welcome to Overwatch Stats"
			}
		},
		methods:{
			getPlayer: function(){
				this.$emit('firstLaunch', false)//Set first launch to false
			}
		}
	}
</script>

<style scoped>


</style>
