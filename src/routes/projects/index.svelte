<script context="module" lang="js">
	export async function load({ fetch }) {
		const res = await fetch('projects/data/projects.json');
		const data = await res.json();
		console.log(data);
		if (res.ok) {
			return {
				props: { projects: data }
			};
		}
	}
</script>

<script>
	export let projects;
	import PageHeader from '../../lib/components/page-header/page-header.svelte';
</script>

<svelte:head>
	<title>Tech Air - Projects</title>
</svelte:head>

<PageHeader title="Projects" backgroundImageUrl="images/sparks.jpg" />

<section>
	<div class="content">
		<p class="introlang">
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Magni quia minima placeat
			perspiciatis a illum labore laboriosam, possimus cupiditate, dignissimos provident, velit quo.
			Officia iure aliquid explicabo reprehenderit, alias consequuntur?
		</p>
	</div>
	<div class="portholder">
		{#each projects as project}
			<div class="portitem" data-aos="flip-left" data-aos-delay="000">
				<a href={`/projects/${project.slug}`}>
					<img
						src={`projects/images/${project.images[0]}`}
						alt={project.name + ' thumbnail image'}
					/>
				</a>
				<h4>{project.name}</h4>
			</div>
		{/each}
	</div>
</section>

<style lang="scss">
	@import '../../mixins.scss';
	@import '../../variables.scss';

	.page-header {
		@include section-header();
		margin: 2rem 0 3rem 0;
	}

	section {
		margin: 0 auto;
		padding: 1rem 10rem;

		@media (max-width: $device-medium) {
			padding: 1rem;
		}
	}

	.content {
		max-width: 900px;
		width: 100%;
		padding: 0 15px;
		margin: 0 auto 50px;
		.introlang {
			color: var(--secondary-font-color);
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
