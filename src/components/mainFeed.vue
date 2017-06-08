<template>

	<div @mousedown="dragWindow" class="mainFeed">

			<div class="container-fluid scroll-tiles">
				<div class="row" id="scroll-area">

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
		<div class="row">

			<div class="col-xs-6 feed-tile-medium" style="background-color:blue">
				<div class="">
						<p>testing 123</p>
				</div>
			</div>

			<div class="col-xs-6 feed-tile-medium" style="background-color:orange">
				<div class="">

				</div>
			</div>

			<div class="col-xs-6 feed-tile-medium" style="background-color:grey">
				<div class="">

				</div>
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
				json_response: "No response data"
			}
		},
		created() {
        setTimeout(function() {
					$('#scroll-area').on('mousewheel', function(event) {
							console.log(event.deltaX, event.deltaY, event.deltaFactor, event.currentTarget.scrollLeft, event, event.originalEvent);
							if (event.originalEvent.deltaY == -100){
								this.scrollLeft -= 50;
							}else{
									this.scrollLeft += 50;
							}
					});
        }, 1);
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
