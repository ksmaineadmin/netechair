<script context="module" lang="js">
	export async function load({ fetch, params }) {
		const res = await fetch('/data/projects.json');
		const data = await res.json();
		const currentlySelectedProject = data.projects.find((p) => p.slug === params.slug);
		if (res.ok) {
			return {
				props: { project: currentlySelectedProject }
			};
		}
	}
</script>

<script lang="js">
	export const prerender = true;
	import PageHeader from '../../lib/components/page-header/page-header.svelte';
	export let project;
</script>

<PageHeader title={project.name} backgroundImageUrl="../images/sparks.jpg" />

<section>
	<div class="portfolio__container">
		<div class="portfolio__details">
			<h2 class="portfolio__title">Project Description</h2>
			<p>Description coming soon</p>
			<div class="divider" />
			<h2 class="portfolio__title">Client</h2>
			<p>{project.name}</p>
			<div class="divider" />
			<!-- <h2 class="portfolio__title">Project Date</h2>
			<p>27 August 2020</p> -->
		</div>
		<div class="portfolio__gallery">
			{#if project?.images?.length}
				{#each project.images as image, index}
					<div class={index === 0 ? 'span-full' : ''}>
						<img src={`${image}`} alt={project.name + ' thumbnail image'} loading="lazy" />
					</div>
				{/each}
			{/if}
		</div>
	</div>
</section>

<style lang="scss">
	@import '../../mixins.scss';
	@import '../../variables.scss';

	.portfolio {
		&__container {
			padding: 3rem;
			max-width: $device-large;
			margin: 0 auto;
			display: grid;
			grid-template-columns: 4fr 8fr;
			gap: 2rem;
			justify-content: center;
			width: 100%;
		}

		&__details {
			p {
				font-size: 1.075rem;
				color: var(--secondary-font-color);
			}
		}
		&__title {
			margin-bottom: 1rem;
			font-size: 1.5rem;
			color: var(--accent-color);
		}

		&__gallery {
			width: 100%;
			display: grid;
			grid-template-columns: 1fr 1fr;
			gap: 1rem;

			img {
				max-width: 100%;
			}
		}
	}

	.divider {
		height: 2px;
		width: 1rem;
		background-color: var(--secondary-font-color);
		opacity: 0.4;
		margin: 3.5rem 0;
	}

	@media screen and (max-width: $device-medium) {
		.portfolio {
			&__container {
				grid-template-columns: 1fr;
			}

			&__details {
				p {
					font-size: 1.075rem;
					color: var(--secondary-font-color);
				}
			}
			&__title {
				margin-bottom: 1rem;
				font-size: 1.5rem;
				color: var(--accent-color);
			}

			&__gallery {
				grid-template-columns: 1fr;

				img {
					max-width: 100%;
				}
			}
		}
	}
</style>
