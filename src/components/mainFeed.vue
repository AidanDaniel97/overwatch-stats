<template>

	<div @mousedown="dragWindow" class="mainFeed">



					<!--<div class="container-fluid">
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
				</div>-->


				<div class="container-fluid scroll-tiles">
					<div class="row scroll-area-stats" id="scroll-area" >
						<div class="col-xs-12 feed-tile-medium stat-card">
							<div class="bg-icon"><svg viewBox="0 0 32 32" class="icon">
			<path d="M9.76,23.52c-0.17,0.8-0.35,1.61-0.49,2.22c-0.06,0.27,0.23,0.49,0.47,0.34c1.45-0.85,3.92-2.36,4.33-2.61
	        c0.46-0.28,0.82-0.14,1.02,0.35c0.04,0.1,0.2,0.45,0.42,0.93c-0.42,0.2-0.88,0.29-1.36,0.26c-0.05,0-0.09,0.01-0.11,0.04
	        c-0.11-0.01-0.22-0.01-0.32-0.02c-0.03,0-0.05,0-0.07,0.01c-0.15,0-0.26,0.22-0.09,0.29c0.12,0.05,0.24,0.09,0.36,0.13
	        c0.01,0.01,0.02,0.02,0.04,0.02c0.66,0.21,1.33,0.28,2.01,0.22c0.56,1.22,1.27,2.76,1.78,3.9c0.09,0.2,0.38,0.13,0.37-0.09
	        c-0.02-0.74-0.04-1.68-0.05-2.58c0.38-0.05,0.74-0.19,1.09-0.34c0.51-0.23,0.96-0.52,1.22-1.03c0.01-0.01,0.01-0.02,0.01-0.03
	        c0.07-0.15-0.12-0.32-0.25-0.18c-0.51,0.51-1.36,0.62-2.08,0.57c-0.01-0.84,0-1.53,0.02-1.83c0.03-0.47,0.14-0.87,0.7-0.95
	        c0.15-0.02,0.3-0.11,0.43-0.18c0.2-0.1,0.33-0.06,0.46,0.12c0.25,0.33,0.71,1.15,1.06,1.78c0.13,0.24,0.49,0.16,0.51-0.11
	        c0.07-0.97,0.18-2.49,0.45-3.31c1.22-0.93,2.18-2.21,2.72-3.74c0.11-0.07,0.22-0.14,0.34-0.21c0.29-0.12,0.56-0.26,0.82-0.43
	        c0.21-0.1,0.42-0.2,0.64-0.3c-0.12,0.51-0.28,1.01-0.48,1.5c-0.05,0.54-0.28,1.03-0.6,1.48c-0.02,0.01-0.03,0.02-0.05,0.04
	        c-0.09,0.17-0.18,0.33-0.3,0.48c0.04,0.04,0.11,0.05,0.17,0.01c1.45-0.97,2.14-2.37,2.59-4.02c0.35-0.11,0.7-0.22,1.05-0.33
	        c0.71-0.22,3.06-0.83,3.42-0.96c-0.56-0.07-1.1-0.11-1.63-0.17c-0.01,0-0.02-0.01-0.03-0.01c-0.9-0.06-1.79-0.12-2.69-0.18
	        c0.07-1.56-1.12-3.24-2.07-4.35c-0.09-0.1-0.22-0.04-0.25,0.07c0.04,0.08,0.07,0.16,0.1,0.24c0.04,0.05,0.08,0.09,0.12,0.14
	        c0.58,1.2,0.89,2.51,0.91,3.83l-1.58-0.11c-0.09-1.31-0.5-2.56-1.17-3.66c0-0.14,0.01-0.28,0.05-0.43c0.21-0.88,0.95-2.42,1.41-3.32
	        c0.14-0.27-0.12-0.57-0.41-0.48c-1.31,0.43-3.84,1.26-4.22,0.92c-0.11-0.1-0.2-0.18-0.32-0.24c-1.19-0.57-2.44-0.76-3.75-0.58
	        c-0.22,0.03-0.39,0-0.54-0.17c-0.1-0.11-0.37-0.4-0.72-0.79c0.78-0.23,1.58-0.34,2.37-0.34c0.05,0,0.08-0.03,0.1-0.07
	        c0.15-0.01,0.25-0.22,0.08-0.29c-1.1-0.45-2.25-0.53-3.4-0.22c-0.7-0.76-1.5-1.63-2.13-2.31c-0.19-0.2-0.52-0.02-0.46,0.24
	        c0.37,1.53,0.65,3.07,0.91,4.62c0.03,0.2,0.05,0.39,0.04,0.56c-0.49,0.28-0.95,0.6-1.38,0.97C10.57,8.4,9.49,7.68,8.46,6.96
	        c0.08-0.07,0.17-0.13,0.26-0.2C8.7,6.76,8.68,6.74,8.67,6.73c0.37-0.28,0.76-0.51,1.19-0.69C10.02,5.97,10,5.73,9.81,5.73
	        c-0.15,0-0.32,0-0.49,0.01C8.68,5.65,8.1,5.95,7.64,6.39c-0.57-0.4-1.11-0.77-1.52-1.06C5.94,5.21,5.72,5.43,5.85,5.6
	        c0.31,0.42,0.71,0.96,1.13,1.55c-0.52,0.69-0.71,1.53-0.69,2.4c0,0.18,0.27,0.21,0.31,0.04C6.76,8.98,7.04,8.46,7.45,8
	        c0,0,0.01,0.01,0.01,0.01c0.03-0.04,0.05-0.07,0.08-0.11c0.79,1.09,1.6,2.24,2.1,3.01c-0.35,0.61-0.63,1.28-0.82,2
	        c-0.09,0.34-0.15,0.67-0.19,1.01c-0.1,0.02-0.19,0.03-0.29,0.04c-0.01-0.03-0.02-0.07-0.04-0.1c0-0.02-0.01-0.05-0.01-0.07
	        c-0.01,0-0.01,0-0.02,0c-0.3-0.92-0.29-1.87,0.04-2.8c0.02-0.06,0.01-0.1-0.02-0.13c0-0.14-0.21-0.23-0.3-0.08
	        c-0.64,1.08-0.95,2.25-0.93,3.5c-2.26,0.78-4.55,1.43-6.87,1.97c-0.25,0.06-0.25,0.41,0,0.47c3.24,0.73,6.44,1.59,9.61,2.59
	        c0.19,0.31,0.41,0.61,0.64,0.89c0,0.1-0.01,0.19-0.03,0.29c-0.05,0.27-0.2,0.97-0.38,1.81 M18.11,15.73l-0.15,0.78l-1.02-0.31
	        l-1.83,1.72l0.34-1.6l-0.4-0.58l0.46,0.24l0.06-0.22l-0.54-0.48h-0.48L15,14.45l-0.55-0.54l1.53-1.47l0.12-0.94l0.78,0.9l0.54,0.01
	        l0.19,0.18l0.64-0.13l0.06,0.66l0.27,0.28l0.07,0.52l0.67,0.72l-0.46,0.12l-0.21,0.27l0.75,0.49L18.11,15.73z"></path>
		</svg></div>
								<div class="card-content">
								<h3 class="card-heading">{{this.userData.userData.userData[this.userData.userData.userRegion].stats.quickplay.average_stats.damage_done_avg.toLocaleString()}}</h3>
								<p class="card-copy">Damage Done - Average</p>
							</div>
						</div>

						<div class="col-xs-12 feed-tile-medium stat-card">
								<div class="bg-icon">
									<svg viewBox="0 0 32 32" class="icon">
										<path fill="none" d="M16.8,7.2v0.9c3.8,0.4,6.8,3.4,7.2,7.2h0.9C24.4,11,21,7.6,16.8,7.2z"></path>
										<path fill="none" d="M16.8,23.9v0.9c4.3-0.4,7.7-3.8,8-8h-0.9C23.6,20.5,20.5,23.6,16.8,23.9z"></path>
										<path fill="none" d="M8.1,16.8H7.2c0.4,4.3,3.8,7.7,8,8v-0.9C11.5,23.6,8.4,20.5,8.1,16.8z"></path>
										<path fill="none" d="M15.2,8.1V7.2c-4.3,0.4-7.7,3.8-8,8h0.9C8.4,11.5,11.5,8.4,15.2,8.1z"></path>
										<path d="M15.2,7.2V3.5C8.9,3.9,3.9,8.9,3.5,15.2h3.7C7.6,11,11,7.6,15.2,7.2z"></path>
										<path d="M24.8,15.2h3.7C28.1,8.9,23.1,3.9,16.8,3.5v3.7C21,7.6,24.4,11,24.8,15.2z"></path>
										<path d="M7.2,16.8H3.5c0.4,6.3,5.4,11.4,11.7,11.7v-3.7C11,24.4,7.6,21,7.2,16.8z"></path>
										<path d="M16.8,24.8v3.7c6.3-0.4,11.4-5.4,11.7-11.7h-3.7C24.4,21,21,24.4,16.8,24.8z"></path>
										<path d="M21.5,16c0-0.4,0.3-0.8,0.8-0.8h1.7c-0.4-3.8-3.4-6.8-7.2-7.2v1.7c0,0.4-0.3,0.8-0.8,0.8s-0.8-0.3-0.8-0.8V8.1
														c-3.8,0.4-6.8,3.4-7.2,7.2h1.7c0.4,0,0.8,0.3,0.8,0.8c0,0.4-0.3,0.8-0.8,0.8H8.1c0.4,3.8,3.4,6.8,7.2,7.2v-1.7
														c0-0.4,0.3-0.8,0.8-0.8s0.8,0.3,0.8,0.8v1.7c3.8-0.4,6.8-3.4,7.2-7.2h-1.7C21.8,16.8,21.5,16.4,21.5,16z M15.2,18.6
														c-1.2-1.9-3-2.4-3-2.4L14,15c0.7,0.7,1.1,1.9,1.1,1.9c0.8-2.3,2.5-4.1,2.5-4.1l1.5,1.6C16.4,15.9,15.2,18.6,15.2,18.6z"></path>
									</svg>
								</div>
								<div class="card-content">
								<h3 class="card-heading">{{this.userData.userData.userData[this.userData.userData.userRegion].stats.quickplay.average_stats.eliminations_avg.toLocaleString()}}</h3>
								<p class="card-copy">Eliminations - Average</p>
							</div>
						</div>

						<div class="col-xs-12 feed-tile-medium stat-card">
							<div class="bg-icon">
								<svg viewBox="0 0 32 32" class="icon">
			<path d="M7,20.3c-0.2,0.9-0.4,1.9-0.5,2.8c1.6,0.3,3.5,0.4,5,0.9c0,0.6,0,2.9,0,3.3
	        c0.6,0.2,4.3,2.6,4.3,2.6s3.7-2.3,4.3-2.6c0.1-0.5,0.1-2.8,0.1-3.5c1.7-0.3,3.3-0.5,5-0.8c-0.2-1-0.4-1.9-0.6-2.9
	        c1.5-2.3,3-4.7,4.6-7c-0.9-1.7-1.8-3.4-2.6-5.3c-0.2-0.6-0.5-1.3-0.8-2c-0.1-0.1-0.1-0.2-0.2-0.2c-2.4-1.9-5.1-3-7.9-3.6
	        c-0.3,0-0.6,0-0.9,0c-4,0.2-9.3,0.2-11.3,5.1C4.5,9.4,3.8,11.7,3.1,14C4.4,16.1,5.8,18.1,7,20.3z M19,16.5c0.7-0.3,1.7-1.5,2.4-2.2
	        c0.4-0.3,0.8-0.8,1.2-1.1c0.4-0.4,0.9-0.9,1.2-1c1-0.4,2.2-0.1,3.5-0.6c0.4,0.2-1.2,0.4-1.6,0.6c-0.7,1-0.7,2.4-1.4,3.4
	        c-0.6,1-1.6,1.5-2.2,2.4c-1-0.2-2.6,0.3-3.5,0c-0.5-0.2-0.5-0.6-0.8-0.9c-0.6-0.1-1,0.1-1.6,0.1C17.3,16.7,18.2,16.9,19,16.5z
	         M15.9,19.2c0.5,1.3,1.3,2.3,1.7,3.7c-0.7,0.4-1.2,1.1-2,1.5c-0.5-0.6-1.1-1-1.7-1.5c0.4-1.5,1.3-2.4,1.7-3.8
	        C15.8,19,15.9,19.1,15.9,19.2z M7.7,12.2c0.8,0.4,1.6,1.4,2.4,2.2c0.9,0.8,1.8,1.5,2.4,2.2c1,0.1,1.8,0.4,2.8,0.5
	        c-0.4,0.3-0.9-0.1-1.5,0c-0.5,0.1-0.4,0.8-0.8,0.9c-1.4-0.2-2.5,0.3-3.5,0c-0.5-0.1-2-1.8-2.3-2.4c-0.6-1-0.8-2.5-1.3-3.4
	        C5.4,12,4.7,12,4.3,11.7c0,0-0.1,0-0.1,0C4.6,11.5,7,11.9,7.7,12.2z"></path>
		</svg></div>
								<div class="card-content">
								<h3 class="card-heading">{{this.userData.userData.userData[this.userData.userData.userRegion].stats.quickplay.average_stats.deaths_avg.toLocaleString()}}</h3>
								<p class="card-copy">Deaths - Average</p>
							</div>
						</div>

						<div class="col-xs-12 feed-tile-medium stat-card">
							<div class="bg-icon">
								<svg viewBox="0 0 32 32" class="icon">
			<path d="M20.2,21.4c0,0.3-0.1,0.4-0.1,0.6c-0.1,0.5-0.5,0.9-1,1c-0.5,0.1-1.1-0.2-1.3-0.7
                c-0.3-0.7-0.4-1.4,0-2.2c0.3-0.6,0.7-1.2,1.2-1.7c1.4-1.2,0.9-5-0.2-5.8c0,0.9-0.9,3.4-3.5,4.2c-2,0.9-4.2,3.3-3.2,6.9
                c0.2,0.7-0.2,1.7-1.4,1.4c-0.3,0-0.6-0.3-0.9-0.4c-0.1,0-0.2-0.1-0.2,0c0,0,0,0.1,0,0.2c0.3,1.2,1,2.2,2,3c0.8,0.7,1.7,1.2,2.7,1.5
                c0,0,0.1,0,0.1,0.1c-0.3,0.1-0.5,0-0.8,0C11.2,29,9,28,7.3,26.2c-1.3-1.4-2.2-3-2.4-5c-0.2-2.3,0.4-4.4,1.9-6.1
                c0.9-1,1.9-1.9,3.1-2.6c0.5-0.3,1-0.5,1.6-0.7c0.4-0.1,0.4-0.1,0.4,0.3c-0.1,0.5-0.1,1,0.3,1.4c0.5,0.5,1.2,0.7,1.9,0.4
                c0.6-0.3,1-1,0.9-1.8c-0.1-0.7-0.3-1.4-0.4-2.1c-0.3-1.7,0-3.3,0.9-4.7c0.8-1.2,1.8-2.1,3-2.7c0.1-0.1,0.3-0.2,0.4-0.1
                c0.1,0.1,0,0.3,0,0.4c-0.4,1-0.4,1.9-0.2,2.9c0.4,1.9,1.6,3.2,2.9,4.6c1.1,1.2,2.3,2.4,3.3,3.8c0.7,1,1,2.1,1.4,3.2
                c1.2,3.1,0.6,5.9-1.4,8.4c-1.2,1.4-2.7,2.4-4.5,3.1c-1,0.4-2,0.6-3.1,0.7c0,0-0.1,0-0.2,0c0.1-0.1,0.2-0.2,0.3-0.2
                c1.5-0.4,2.6-1.4,3.5-2.6c0.2-0.4,0.3-0.8,0.4-1.2C21.4,24.1,21.1,22.7,20.2,21.4z"></path>
		</svg></div>
								<div class="card-content">
								<h3 class="card-heading">{{this.userData.userData.userData[this.userData.userData.userRegion].stats.quickplay.average_stats.final_blows_avg.toLocaleString()}}</h3>
								<p class="card-copy">Final Blows - Average</p>
							</div>
						</div>

						<div class="col-xs-12 feed-tile-medium stat-card">
							<div class="bg-icon">
								<svg viewBox="0 0 32 32" class="icon">
			<path d="M26.3,19.5h-7.2l-1.9,7.2c-0.2,0.6-0.7,1.1-1.4,1.1h-5.1c-1.1,0-2-1.1-1.7-2.1l1.6-6.2h-6
        c-1.1,0-2-1.1-1.7-2.1l1.4-5.3c0.2-0.6,0.7-1.1,1.4-1.1h7.2l1.9-7.2c0.2-0.6,0.7-1.1,1.4-1.1h5.1c1.1,0,2,1.1,1.7,2.1L21.3,11h6
        c1.1,0,2,1.1,1.7,2.1l-1.4,5.3C27.5,19.1,26.9,19.5,26.3,19.5z"></path>
		</svg></div>
								<div class="card-content">
								<h3 class="card-heading">{{this.userData.userData.userData[this.userData.userData.userRegion].stats.quickplay.average_stats.healing_done_avg.toLocaleString()}}</h3>
								<p class="card-copy">Healing Done - Average</p>
							</div>
						</div>

						<div class="col-xs-12 feed-tile-medium stat-card">
							<div class="bg-icon">
								<svg viewBox="0 0 32 32" class="icon">
				<path fill="none" d="M18.5,9.2l-0.1,0.5l-4.9,0l-0.1-0.5c-2,0.7-3.6,2.3-4.4,4.4l0.4,0.1l-0.2,5l-0.2,0c0.7,1.9,2.3,3.5,4.2,4.2
	        	l0.1-0.7l4.9,0.2l0.1,0.5c2-0.7,3.6-2.3,4.3-4.3l-0.8-0.1l0.1-4.9l0.7-0.1C22.1,11.5,20.5,9.9,18.5,9.2z"></path>
				<path fill="none" d="M16,10.4c-3.1,0-5.6,2.5-5.6,5.6s2.5,5.6,5.6,5.6s5.6-2.5,5.6-5.6S19.1,10.4,16,10.4z M16,19.9
				        c-2.1,0-3.9-1.7-3.9-3.9c0-2.1,1.7-3.9,3.9-3.9s3.9,1.7,3.9,3.9C19.9,18.1,18.1,19.9,16,19.9z"></path>
				<g>
				        <path d="M16,3.5C9.1,3.5,3.5,9.1,3.5,16S9.1,28.5,16,28.5S28.5,22.9,28.5,16S22.9,3.5,16,3.5z M16,5.1c1,0,2,0.2,3,0.4l-0.5,3.6
				                c-0.8-0.3-1.6-0.5-2.5-0.5c-0.9,0-1.7,0.2-2.5,0.4l-0.6-3.6C13.9,5.3,14.9,5.1,16,5.1z M5.6,19c-0.3-1-0.4-2-0.4-3c0-1,0.2-2,0.4-3
				                l3.6,0.5c-0.3,0.8-0.4,1.6-0.4,2.5c0,0.9,0.2,1.8,0.5,2.6L5.6,19z M16,26.9c-1,0-2-0.2-3-0.4l0.4-3.6c0.8,0.3,1.7,0.5,2.6,0.5
				                c0.9,0,1.7-0.2,2.5-0.4l0.6,3.6C18.1,26.7,17.1,26.9,16,26.9z M16,21.6c-3.1,0-5.6-2.5-5.6-5.6s2.5-5.6,5.6-5.6s5.6,2.5,5.6,5.6
				                S19.1,21.6,16,21.6z M22.8,18.5c0.3-0.8,0.5-1.6,0.5-2.5s-0.2-1.8-0.5-2.6l3.6-0.4c0.3,0.9,0.4,1.9,0.4,3c0,1.1-0.2,2.1-0.4,3.1
				                L22.8,18.5z"></path>
				        <circle cx="16" cy="16" r="3.9"></circle>
				</g>
			</svg></div>
								<div class="card-content">
								<h3 class="card-heading">{{this.userData.userData.userData[this.userData.userData.userRegion].stats.quickplay.average_stats.objective_kills_avg.toLocaleString()}}</h3>
								<p class="card-copy">Objective Kills - Average</p>
							</div>
						</div>

						<div class="col-xs-12 feed-tile-medium stat-card">
							<div class="bg-icon">
								<svg viewBox="0 0 32 32" class="icon">
								<path fill="none" d="M16.8,7.2v0.9c3.8,0.4,6.8,3.4,7.2,7.2h0.9C24.4,11,21,7.6,16.8,7.2z"></path>
								<path fill="none" d="M16.8,23.9v0.9c4.3-0.4,7.7-3.8,8-8h-0.9C23.6,20.5,20.5,23.6,16.8,23.9z"></path>
								<path fill="none" d="M8.1,16.8H7.2c0.4,4.3,3.8,7.7,8,8v-0.9C11.5,23.6,8.4,20.5,8.1,16.8z"></path>
								<path fill="none" d="M15.2,8.1V7.2c-4.3,0.4-7.7,3.8-8,8h0.9C8.4,11.5,11.5,8.4,15.2,8.1z"></path>
								<path d="M15.2,7.2V3.5C8.9,3.9,3.9,8.9,3.5,15.2h3.7C7.6,11,11,7.6,15.2,7.2z"></path>
								<path d="M24.8,15.2h3.7C28.1,8.9,23.1,3.9,16.8,3.5v3.7C21,7.6,24.4,11,24.8,15.2z"></path>
								<path d="M7.2,16.8H3.5c0.4,6.3,5.4,11.4,11.7,11.7v-3.7C11,24.4,7.6,21,7.2,16.8z"></path>
								<path d="M16.8,24.8v3.7c6.3-0.4,11.4-5.4,11.7-11.7h-3.7C24.4,21,21,24.4,16.8,24.8z"></path>
								<path d="M21.5,16c0-0.4,0.3-0.8,0.8-0.8h1.7c-0.4-3.8-3.4-6.8-7.2-7.2v1.7c0,0.4-0.3,0.8-0.8,0.8s-0.8-0.3-0.8-0.8V8.1
								        c-3.8,0.4-6.8,3.4-7.2,7.2h1.7c0.4,0,0.8,0.3,0.8,0.8c0,0.4-0.3,0.8-0.8,0.8H8.1c0.4,3.8,3.4,6.8,7.2,7.2v-1.7
								        c0-0.4,0.3-0.8,0.8-0.8s0.8,0.3,0.8,0.8v1.7c3.8-0.4,6.8-3.4,7.2-7.2h-1.7C21.8,16.8,21.5,16.4,21.5,16z M16,12.5
								        c0.6,0,1.2,0.5,1.2,1.2s-0.5,1.2-1.2,1.2c-0.6,0-1.2-0.5-1.2-1.2C14.8,13,15.4,12.5,16,12.5z M17.7,18.2c0,0.4-0.4,0.8-0.8,0.8H15
								        c-0.4,0-0.8-0.4-0.8-0.8v-1.9c0-0.4,0.4-0.8,0.8-0.8H17c0.4,0,0.8,0.4,0.8,0.8V18.2z"></path>

							</svg></div>
								<div class="card-content">
									<h3 class="card-heading">{{this.userData.userData.userData[this.userData.userData.userRegion].stats.quickplay.average_stats.solo_kills_avg.toLocaleString()}}</h3>
									<p class="card-copy">Solo Kills- Average</p>
								</div>
						</div>

						<div class="col-xs-12 feed-tile-medium stat-card">
							<div class="bg-icon">
								<svg viewBox="0 0 32 32" class="icon">
									<path d="M20.2,21.4c0,0.3-0.1,0.4-0.1,0.6c-0.1,0.5-0.5,0.9-1,1c-0.5,0.1-1.1-0.2-1.3-0.7
														c-0.3-0.7-0.4-1.4,0-2.2c0.3-0.6,0.7-1.2,1.2-1.7c1.4-1.2,0.9-5-0.2-5.8c0,0.9-0.9,3.4-3.5,4.2c-2,0.9-4.2,3.3-3.2,6.9
														c0.2,0.7-0.2,1.7-1.4,1.4c-0.3,0-0.6-0.3-0.9-0.4c-0.1,0-0.2-0.1-0.2,0c0,0,0,0.1,0,0.2c0.3,1.2,1,2.2,2,3c0.8,0.7,1.7,1.2,2.7,1.5
														c0,0,0.1,0,0.1,0.1c-0.3,0.1-0.5,0-0.8,0C11.2,29,9,28,7.3,26.2c-1.3-1.4-2.2-3-2.4-5c-0.2-2.3,0.4-4.4,1.9-6.1
														c0.9-1,1.9-1.9,3.1-2.6c0.5-0.3,1-0.5,1.6-0.7c0.4-0.1,0.4-0.1,0.4,0.3c-0.1,0.5-0.1,1,0.3,1.4c0.5,0.5,1.2,0.7,1.9,0.4
														c0.6-0.3,1-1,0.9-1.8c-0.1-0.7-0.3-1.4-0.4-2.1c-0.3-1.7,0-3.3,0.9-4.7c0.8-1.2,1.8-2.1,3-2.7c0.1-0.1,0.3-0.2,0.4-0.1
														c0.1,0.1,0,0.3,0,0.4c-0.4,1-0.4,1.9-0.2,2.9c0.4,1.9,1.6,3.2,2.9,4.6c1.1,1.2,2.3,2.4,3.3,3.8c0.7,1,1,2.1,1.4,3.2
														c1.2,3.1,0.6,5.9-1.4,8.4c-1.2,1.4-2.7,2.4-4.5,3.1c-1,0.4-2,0.6-3.1,0.7c0,0-0.1,0-0.2,0c0.1-0.1,0.2-0.2,0.3-0.2
														c1.5-0.4,2.6-1.4,3.5-2.6c0.2-0.4,0.3-0.8,0.4-1.2C21.4,24.1,21.1,22.7,20.2,21.4z"></path>
								</svg></div>
								<div class="card-content">
								<h3 class="card-heading">{{this.userData.userData.userData[this.userData.userData.userRegion].stats.quickplay.average_stats.time_spent_on_fire_avg.toLocaleString()}}</h3>
								<p class="card-copy">Time on Fire - Average</p>
							</div>
						</div>

				</div>
				</div>











			<div class="container-fluid scroll-tiles">
				<div class="row scroll-area-guides" id="scroll-area" >

					<div v-for="guide in heroGuides[currentHero]" class="col-xs-12 feed-tile-medium stat-card">



						<div class="col-xs-12 feed-tile-medium ">
							<a target="_blank" :href="guide.link">
								<div class="bg-icon-guides">
									<img :src="'src/assets/img/hero-icons/' + currentHero + '.svg'">
								</div>
								<div class="card-content">

										<h2 class="guide-tile-name">{{guide.name}}</h2>

							</div>
							</a>
						</div>
					</div>
				</div>
			</div>




	<div class="container-fluid scroll-tiles">
		<div class="row scroll-area" id="streams-scroll-area" >
				<div v-for="stream in twitchStreams" class="col-xs-6 feed-tile-medium" :style="{ 'background-image': 'url(' + stream.preview.medium + ')' }" style="padding:0px;cursor:pointer;background-size: cover;">
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
		props: {
			userData: app.userData, // you need to give the parent components' data here.
			currentHero: app.currentHero
		 },
		data(){
			return{
				twitchStreams: [],
				heroGuides: [], 
			}
		},
		created: function() {
				var scrollbarTimeout;
				setTimeout(function() {
					$('.scroll-area').on('mousewheel', function(event) {
							if (event.originalEvent.deltaY == -100){
								this.scrollLeft -= 185;
							}else{
									this.scrollLeft += 185;
							}
					});

					$('.scroll-area-guides').on('mousewheel', function(event) {
							if (event.originalEvent.deltaY == -100){
								this.scrollLeft -= 370;
							}else{
									this.scrollLeft += 370;
							}
					});

					$('.scroll-area-stats').on('mousewheel', function(event) {
							if (event.originalEvent.deltaY == -100){
								this.scrollLeft -= 370;
							}else{
									this.scrollLeft += 370;
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

				console.log("loading guides");
				this.$http.get('https://www.jasonbase.com/things/5ykP.json')
					.then(response => {
						this.heroGuides = response.body;
						console.log(this.heroGuides)

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
