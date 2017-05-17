<template>
	<div class="newUser">
		<nav class="navbar navbar-default">
		  <div class="container-fluid">
		    <div class="navbar-header">
		      <a class="navbar-brand" href="#"> 
		      </a>
		    </div>
		  </div>
		</nav>


		<div class="container-fluid">
			<div class="col-sm-12"><h1>{{message}}</h1></div>
			<div class="col-sm-12"><p>{{intro}}</p></div>
			<div class="col-sm-12">
				<input v-model="user.battlenetName" placeholder="Moosey#2314">

				<select v-model="user.region">
				  <option disabled value="">Please select one</option>
				  <option>EU</option>
				  <option>US</option>
				  <option>KR</option>
				</select>


				<div class="col-sm-12"><p>{{user.battlenetName}}</p></div>

				<div class="col-sm-12"><p>{{user.region}}</p></div>

				<button v-on:click="getPlayer">Test</button>

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
				message: "Welcome to Overwatch Stats",
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
							 console.log(this.user.quickplayStats, this.user.competitiveStats);

							 console.log(this.user.quickplayStats.overall_stats.wins)
            });
			}


		}
	}
</script>

<style scoped>


</style>
