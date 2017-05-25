<template>
	<div class="newUser">
		
		<div class="container-fluid">
			<div class="row">
				<div class="col-xs-12"><h1 class="app-title">{{message}}</h1></div>
			</div>

			<div class="col-xs-12 login-button">
				<button v-on:click="getPlayer" class="overwatch-button-primary">Start</button>
			</div>

			<!--<img :src="this.user.avatar" width="400" height="400"/>-->



			</div>
		</div>
	</div>
</template>

<script>
	export default{
		name: "newUser",
		data(){
			return{
				message: "mini stats",
				user:{
					battlenetName: "",
					region: "",
					quickplayStats: "",
					avatar: "",
					competitiveStats: "",
					statsRoute: ""
				},
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
			},
		}
	}
</script>

<style scoped>
	.navbar{
		height:30px;
	}
</style>
