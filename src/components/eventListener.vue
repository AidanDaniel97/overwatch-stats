<template>
	<div class="eventListener">
	</div>
</template>

<script>
	export default{
		name: "eventListener",
		data(){
			return{
				game_features: ['kills','death','preGame','postGame','player']
			}
		},
		created: function(){
			console.log("Event listner started");
			var vueThis = this;
			overwolf.games.getRunningGameInfo(function(gameInfo){
				if (vueThis.gameLaunched(gameInfo)) {
					 vueThis.registerEvents();
					 setTimeout(vueThis.setFeatures, 1000);
				 }
				overwolf.games.onGameInfoUpdated.addListener(function (res) {
					//vueThis.$emit("gameEvent", res)
					console.log("info updated " , res )
					if (vueThis.gameLaunched(res)) {
						 vueThis.registerEvents();
						 setTimeout(vueThis.setFeatures, 1000);
					 }
				});
			});

		},
		methods:{
			gameLaunched: function(gameInfoResult) {

				if (gameInfoResult.gameInfo){
				  //note: we divide by 10 to get the game class id without it's sequence number
				  if (Math.floor(gameInfoResult.gameInfo.id/10) == 10844) {
				    console.log("this game is OW");

						if (gameInfoResult.gameInfo.isRunning) {
							return true;
						}

				  }else{
						return false;
					}

				}else{
					if (gameInfoResult.isRunning){
						console.log("Game detected");
						return true
					}else{
						return false;
						console.log("No game detected");
					}
				}
			},

			setFeatures: function() {
				var vueThis = this;
			  overwolf.games.events.setRequiredFeatures(vueThis.game_features, function(info) {
			    if (info.status == "error")
			    {
			      //console.log("Could not set required features: " + info.reason);
			      //console.log("Trying in 2 seconds");
			      window.setTimeout(vueThis.setFeatures, 2000);
			      return;
			    }

			    console.log("Set required features:");
			    console.log(JSON.stringify(info));
			  });
			},

		 registerEvents: function() {
			 		var vueThis = this;
				  // general events errors
				  overwolf.games.events.onError.addListener(function(info) {
				    //console.log("Error: " + JSON.stringify(info));
						vueThis.$emit("gameEvent", info);
				  });

				  // "static" data changed
				  // This will also be triggered the first time we register
				  // for events and will contain all the current information
				  overwolf.games.events.onInfoUpdates2.addListener(function(info) {
				    //console.log("Info UPDATE: " + JSON.stringify(info));
						vueThis.$emit("gameEvent", info);
				  });

				  // an event triggerd
				  overwolf.games.events.onNewEvents.addListener(function(info) {
				    //console.log("EVENT FIRED: " + JSON.stringify(info));
						vueThis.$emit("gameEvent", info);
				  });
				}

		},
	}






</script>

<style scoped>


</style>
