<template>

	<div class="guidesWindow">

		<h1 class="guidesHeader">{{currentGuide.name}}</h1>

		<iframe class="guidesContainer" height="315" :src="currentGuide.link" frameborder="0">

		</iframe>




	</div>
</template>

<script>
	export default{
		name: "guidesWindow",
		props: {
			currentGuide: app.currentGuide, // you need to give the parent components' data here.
		 },
		data(){
			return{
				guideTest: []
			}
		},
		created: function() {
		


    },
		methods:{

	}
	}





</script>

<style scoped>
	.navbar{
		height:30px;
	}


	/*background image
	set the background image to be hero name + "-background.png/jpg" to reduce if statements for every single hero

	*/
</style>
