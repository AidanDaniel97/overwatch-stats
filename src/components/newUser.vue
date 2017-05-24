<template>
	<div class="newUser">
		<nav  @mousedown="dragWindow" class="navbar navbar-default">
		  <div class="container-fluid">
		    <div class="navbar-header">
					<a  @mousedown="closeWindow" class="navbar-brand" href="#">
						&#10006;
					</a>
		      <a  @mousedown="minimizeWindow" class="navbar-brand minimize" href="#">
						&#128469;
		      </a>
		    </div>
		  </div>
		</nav>


		<div class="container-fluid">
			<div class="col-xs-12"><h1 class="app-title">{{message}}</h1></div>
			<div class="col-xs-12"><p class="app-intro">{{intro}}</p></div>

			<div class="col-xs-6 col-xs-offset-1 input-box">
				<input class="username" v-model="user.battlenetName" placeholder="Moosey-2314">
			</div>
			<div class="col-xs-4 input-box">
				<select v-model="user.region" class="region">
				  <option disabled value="">Region</option>
				  <option>EU</option>
				  <option>US</option>
				  <option>KR</option>
				</select>
			</div>


			<div class="col-xs-12 login-button">
				<button v-on:click="getPlayer" class="overwatch-button-primary">Start</button>
			</div>

			<!--<img :src="this.user.avatar" width="400" height="400"/>-->

			<div>{{json_response}}</div>


			</div>
		</div>
	</div>
</template>

<script>
	export default{
		name: "newUser",
		data(){
			return{
				message: "Overwatch HQ",
				intro: "Please enter your Battlenet name & region.",
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
			getPlayer: function(){
					this.$http.get('https://owapi.net/api/v3/u/'+ this.user.battlenetName + '/stats?platform=pc')
						.then(response => {
							 this.getTemp = response.data;
							 console.log(response.data);
			// or like this this.getTemp = response.json()
							 this.json_response = response.data;
							 this.user.quickplayStats = response.data[this.user.region.toLowerCase()].stats.quickplay
							 this.user.competitiveStats = response.data[this.user.region.toLowerCase()].stats.competitive
							 this.user.avatar = response.data[this.user.region.toLowerCase()].stats.quickplay.overall_stats.avatar
							 this.$emit("playerSet",this.user);
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
