<template>
	<div @mousedown="dragWindow" @contextmenu="toggleFeed" class="miniStats" style="background-image:url('src/assets/img/pharah-background.png');border-radius:3px;">

		<div class="container-fluid">
			<div class="row">
				<div class="col-xs-3 portrait-holder">
					<img :src="this.userData.userData[this.user.region].stats.quickplay.overall_stats.avatar" class="player-portrait">
				</div>
				<div class="col-xs-6">
					<p>Moosey#2314</p>
					<p>Level 7</p>
				</div>
				<div class="col-xs-offset-2 col-xs-1 stats-controls">
					<a  @mousedown="closeWindow" class="stats-close" href="#">
						&#10006;
					</a>
			</div>

			</div>

			<!--<img :src="this.user.avatar" width="400" height="400"/>-->



			</div>
		</div>
	</div>
</template>

<script>
	export default{
		name: "miniStats",
		data(){
			return{
				message: "mini stats",
				user:{
					battlenetName:  this.userData.userbattlenet,
					region:  this.userData.userRegion,
					quickplayStats: "",
					avatar: "",
					competitiveStats: "",
					statsRoute: ""
				},
				json_response: "No response data"
			}
		},
		props: {
			userData: app.userData, // you need to give the parent components' data here.
			userRegion: "eu"
		 },
		methods:{
			dragWindow: function(){
				overwolf.windows.getCurrentWindow(function(result) {
					if(result.status === "success") {
			        overwolf.windows.dragMove(result.window.id);
			    }
				});
			},
			closeWindow: function(){
				overwolf.windows.getCurrentWindow(function(result) {
					if(result.status === "success") {
			        overwolf.windows.close(result.window.id);
			    }
				});
			},
			minimizeWindow: function(){
				overwolf.windows.getCurrentWindow(function(result) {
					if(result.status === "success") {
			        overwolf.windows.minimize(result.window.id);
			    }
				});
			},
			toggleFeed: function(){
				console.log("Toggled")
				console.log(this.user.region)
				console.log()
			}
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
