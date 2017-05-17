<template>
	<div class="newUser">
		<nav  @mousedown="dragWindow" class="navbar navbar-default">
		  <div class="container-fluid">
		    <div class="navbar-header">
		      <a class="navbar-brand" href="#">
		      </a>
		    </div>
		  </div>
		</nav>


		<div class="container-fluid">
			<div class="col-sm-12"><h1 class="app-title">{{message}}</h1></div>
			<div class="col-sm-12"><p class="app-intro">{{intro}}</p></div>
			<div class="col-sm-12">
				<input v-model="user.battlenetName" placeholder="Moosey-2314">

				<select v-model="user.region">
				  <option disabled value="">Region</option>
				  <option>EU</option>
				  <option>US</option>
				  <option>KR</option>
				</select>
			</div>

				<div class="col-sm-12"><p>{{user.battlenetName}}</p></div>

				<div class="col-sm-12"><p>{{user.region}}</p></div>

				<button v-on:click="getPlayer" class="overwatch-button-secondary">Test</button>

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
			}


		}
	}
</script>

<style scoped>
	.navbar{
		height:30px;
	}
</style>
