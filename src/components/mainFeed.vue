<template>
	<div @mousedown="dragWindow" class="mainFeed" style="/*background-image:url('src/assets/img/pharah-background.png')*/;border-radius:3px;">

		<div class="container-fluid">
			<div class="row">
				<div class="col-xs-12 user-data">
					<h1>test Test</h1>
				</div>


			</div>

			<!--<img :src="this.user.avatar" width="400" height="400"/>-->



			</div>
		</div>
	</div>
</template>

<script>
	export default{
		name: "mainFeed",
		data(){
			return{
				json_response: "No response data"
			}
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
