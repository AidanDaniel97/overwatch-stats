<template>
	<div class="eventListener">
	</div>
</template>

<script>
	export default{
		name: "eventListener",
		data(){
			return{
				game_events: ['kills','death','preGame','postGame','player']
			}
		},
	}

/*
	overwolf.games.onGameInfoUpdated.addListener(function (res) {
		console.log("onGameInfoUpdated: " + JSON.stringify(res));
	})*/

</script>

<style scoped>


</style>
