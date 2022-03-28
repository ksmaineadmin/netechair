<script>
	export const prerender = true;
</script>

<svelte:head>
	<title>Tech Air - Projects</title>
</svelte:head>

<div class="content">
	<h1 data-aos="fade-up">Projects</h1>
	<p class="introlang">
		Lorem ipsum dolor sit amet consectetur adipisicing elit. Magni quia minima placeat perspiciatis
		a illum labore laboriosam, possimus cupiditate, dignissimos provident, velit quo. Officia iure
		aliquid explicabo reprehenderit, alias consequuntur?
	</p>
</div>
<div class="portholder">
	<div class="portitem" data-aos="flip-left" data-aos-delay="000">
		<img src="/images/portholder.jpg" alt="alttag" />
		<h4>Project Title Here.</h4>
		<p>Project Subtitle can go here.</p>
	</div>
	<div class="portitem" data-aos="flip-left" data-aos-delay="100">
		<img src="/images/portholder.jpg" alt="alttag" />
		<h4>Project Title Here.</h4>
		<p>Project Subtitle can go here.</p>
	</div>
	<div class="portitem" data-aos="flip-left" data-aos-delay="200">
		<img src="/images/portholder.jpg" alt="alttag" />
		<h4>Project Title Here.</h4>
		<p>Project Subtitle can go here.</p>
	</div>
	<div class="portitem" data-aos="flip-left" data-aos-delay="300">
		<img src="/images/portholder.jpg" alt="alttag" />
		<h4>Project Title Here.</h4>
		<p>Project Subtitle can go here.</p>
	</div>
	<div class="portitem" data-aos="flip-left" data-aos-delay="000">
		<img src="/images/portholder.jpg" alt="alttag" />
		<h4>Project Title Here.</h4>
		<p>Project Subtitle can go here.</p>
	</div>
	<div class="portitem" data-aos="flip-left" data-aos-delay="100">
		<img src="/images/portholder.jpg" alt="alttag" />
		<h4>Project Title Here.</h4>
		<p>Project Subtitle can go here.</p>
	</div>
	<div class="portitem" data-aos="flip-left" data-aos-delay="200">
		<img src="/images/portholder.jpg" alt="alttag" />
		<h4>Project Title Here.</h4>
		<p>Project Subtitle can go here.</p>
	</div>
	<div class="portitem" data-aos="flip-left" data-aos-delay="300">
		<img src="/images/portholder.jpg" alt="alttag" />
		<h4>Project Title Here.</h4>
		<p>Project Subtitle can go here.</p>
	</div>
	<div class="portitem" data-aos="flip-left" data-aos-delay="000">
		<img src="/images/portholder.jpg" alt="alttag" />
		<h4>Project Title Here.</h4>
		<p>Project Subtitle can go here.</p>
	</div>
</div>

<style lang="scss">
	.content {
		max-width: 900px;
		width: 100%;
		padding: 0 15px;
		margin: 0 auto 50px;
		.introlang {
			margin-bottom: 60px;
			font-size: 18px;
			line-height: 35px;
		}
	}
	.portholder {
		display: flex;
		flex-wrap: wrap;
		width: 100%;
		justify-content: center;

		.portitem {
			width: 20%;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			padding: 10px;
			margin: 10px 0;
			&:hover img {
				transform: scale(1.08) translateY(-9px);
				filter: grayscale(0);
				transition: all ease-in-out 100ms;
			}
			&:hover h4 {
				color: var(--accent-color);
				transition: all ease-in-out 100ms;
			}

			img {
				width: 100%;
				transition: all ease-in-out 100ms;
				filter: grayscale(1);
			}
			h4 {
				font-size: 20px;
				text-transform: uppercase;
				letter-spacing: 0.7px;
				margin: 10px 0 0 0;
			}
			p {
				margin: 5px;
				font-size: 13px;
			}
			@media only screen and (max-width: 1600px) {
				width: 25%;
			}
			@media only screen and (max-width: 1100px) {
				width: 33%;
			}
			@media only screen and (max-width: 800px) {
				width: 50%;
			}
			@media only screen and (max-width: 560px) {
				width: 100%;
			}
		}
	}
</style>
