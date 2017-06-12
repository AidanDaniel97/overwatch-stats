<template>

	<div @mousedown="dragWindow" class="mainFeed">



					<div class="container-fluid">
						<div class="row">

							<div class="col-xs-4 feed-tile-small">
								<i class="fa fa-pie-chart" aria-hidden="true"></i>
							</div>

							<div class="col-xs-4 feed-tile-small">
								<i class="fa fa-cog" aria-hidden="true"></i>
							</div>

							<div class="col-xs-4 feed-tile-small">
								<i class="fa fa-info" aria-hidden="true"></i>
							</div>

					</div>
				</div>


			<div class="container-fluid scroll-tiles">
				<div class="row scroll-area" id="scroll-area" >

					<div class="col-xs-6 feed-tile-medium" style="background-color:purple">
						<div class="">
							<p>testing 123</p>
						</div>
					</div>

					<div class="col-xs-6 feed-tile-medium" style="background-color:red">
						<div class="">
								<p>testing 123</p>
						</div>
					</div>

					<div class="col-xs-6 feed-tile-medium" style="background-color:green">
						<div class="">
								<p>testing 123</p>
						</div>
					</div>

					<div class="col-xs-6 feed-tile-medium" style="background-color:blue">
						<div class="">

						</div>
					</div>

			</div>
		</div>



		<div class="container-fluid">
			<div class="row">

				<div class="col-xs-12 feed-tile-medium" style="background-color:green">
					<div class="">
							<p>testing 123</p>
					</div>
				</div>

		</div>
	</div>

	<div class="container-fluid scroll-tiles">
		<div class="row scroll-area" id="streams-scroll-area" >
				<div v-for="stream in twitchStreams" class="col-xs-6 feed-tile-medium" :style="{ 'background-image': 'url(' + stream.preview.medium + ')' }" style="padding:0px;cursor:pointer;">
					<a target="_blank" :href="stream.channel.url"><div class="stream-tile-overlay"></div>
					<div class="col-xs-12">
						<h2 class="stream-tile-name">{{stream.channel.name}}</h2>
						<div class="col-xs-12">
							<p><i class="fa fa-user" aria-hidden="true"></i> {{stream.viewers.toLocaleString()}}</p>
						</div>
					</div>
				</a>
				</div>


	</div>
</div>


	</div>
</template>

<script>
	export default{
		name: "mainFeed",
		data(){
			return{
				json_response: "No response data",
				twitchStreams: []
			}
		},
		created: function() {

				setTimeout(function() {
					$('#scroll-area').on('mousewheel', function(event) {
							console.log(event.deltaX, event.deltaY, event.deltaFactor, event.currentTarget.scrollLeft, event, event.originalEvent);
							if (event.originalEvent.deltaY == -100){
								this.scrollLeft -= 50;
							}else{
									this.scrollLeft += 50;
							}
					});

					$('#streams-scroll-area').on('mousewheel', function(event) {
							console.log(event.deltaX, event.deltaY, event.deltaFactor, event.currentTarget.scrollLeft, event, event.originalEvent);
							if (event.originalEvent.deltaY == -100){
								this.scrollLeft -= 50;
							}else{
									this.scrollLeft += 50;
							}
					});
        }, 1);

					console.log("Loading streams");
					this.$http.get('https://api.twitch.tv/kraken/streams/?game=Overwatch&client_id=f7npttcncz50y2s1scs3ze34lh3wse')
						.then(response => {
							console.log(response)
							console.log(this.twitchStreams);
							for (this.i = 0; this.i < 5; this.i++) {
							    this.twitchStreams.push(response.body.streams[this.i]);
							}
							console.log(this.twitchStreams);
				});



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


	/*background image
	set the background image to be hero name + "-background.png/jpg" to reduce if statements for every single hero

	*/
</style>
