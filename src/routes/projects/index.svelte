<script context="module" lang="js">
	export async function load({ fetch }) {
		const res = await fetch('/data/projects.json');
		const data = await res.json();
		if (res.ok) {
			return {
				props: { projects: data.projects }
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
	<div class="project__grid">
		{#each projects as project}
			<!-- data-aos="flip-left" data-aos-delay="000" -->
			<div class="project__cell">
				<a href={`/projects/${project.slug}`}>
					{#if project?.images?.length}
						<img
							src={`${project.images[0]}`}
							class="project__image"
							alt={project.name + ' thumbnail image'}
							loading="lazy"
							title={project.name + ' thumbnail image'}
						/>
					{:else}
						<img
							src="https://via.placeholder.com/150?text=No+image+available"
							class="project__image"
							alt=""
						/>
					{/if}
				</a>
				<a href={`/projects/${project.slug}`} class="project__link">{project.name}</a>
			</div>
		{/each}
	</div>
</section>

<style lang="scss">
	@import '../../mixins.scss';
	@import '../../variables.scss';

	.project {
		&__grid {
			display: grid;
			grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
			gap: 3rem;
			padding: 1rem;
		}

		&__cell {
			display: grid;
			grid-template-columns: 1fr;
			grid-template-rows: 1fr auto;
			text-align: center;
		}

		&__link {
			padding: 1rem;
		}

		&__image {
			object-fit: cover;
			max-height: 220px;
			height: 100%;
			width: 100%;
			border-radius: 2px;
			transition: all ease-in-out 300ms;
			filter: grayscale(1);

			&:hover {
				transform: scale(1.01) translateY(-2px);
				filter: grayscale(0);
				transition: all ease-in-out 300ms;
			}
		}
	}

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
</style>
