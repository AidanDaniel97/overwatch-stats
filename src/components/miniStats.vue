<template>
	<div  @mousedown="dragWindow" @contextmenu="toggleFeed" class="miniStats" style="background-image:url('src/assets/img/pharah-background.png')">

		<div class="container-fluid">
			<div class="row">
				<div class="col-xs-2 portrait-holder">
					<img :src="this.user.avatar" class="player-portrait">
				</div>
				<div class="col-xs-7 user-data">
					<p>{{user.battlenetName}}</p>
					<p>Level {{user.userLevel}}</p>
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
					battlenetName:  this.userData.userData.userbattlenet,
					region:  this.userData.userData.userRegion,
					quickplayStats: "",
					avatar: this.userData.userData.userData[this.userData.userData.userRegion].stats.quickplay.overall_stats.avatar,
					competitiveStats: "",
					statsRoute: "",
					userLevel: this.userData.userData.userData[this.userData.userData.userRegion].stats.quickplay.overall_stats.level,
				},
				json_response: "No response data"
			}
		},
		props: {
			userData: app.userData, // you need to give the parent components' data here.
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

      this.$emit('toggleFeed')
			console.log("Sent emit")

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

<!--
Todo:
add some sort of tracking per match that will show in the mini stats,

death coun, kill count - live stats for the game


-->
