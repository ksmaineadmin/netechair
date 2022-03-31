<script lang="js">
	import PageHeader from '../lib/components/page-header/page-header.svelte';
</script>

<PageHeader title="Project Title" backgroundImageUrl="images/sparks.jpg" />

<section>
	<div class="portfolio__container">
		<div class="portfolio__details">
			<h2 class="portfolio__title">Project Description</h2>
			<p>
				Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has
				been the industry's standard dummy text ever since the 1500s, when an unknown printer took a
				galley of type and scrambled it to make a type specimen book. It has survived not only five
				centuries, but also the leap into electronic typesetting, remaining essentially unchanged.
				It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum
				passages, and more recently with desktop publishing software like Aldus PageMaker including
				versions of Lorem Ipsum.
			</p>
			<div class="divider" />
			<h2 class="portfolio__title">Client</h2>
			<p>Client name here</p>
			<div class="divider" />
			<h2 class="portfolio__title">Project Date</h2>
			<p>27 August 2020</p>
		</div>
		<div class="portfolio__gallery">
			<img
				src="https://images.unsplash.com/photo-1454165804606-c3d57bc86b40?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80"
				class="span-full"
				alt=""
			/>
			<img
				src="https://images.unsplash.com/photo-1522683845419-f46a59d0de42?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80"
				alt=""
			/>
			<img
				src="https://images.unsplash.com/photo-1455165814004-1126a7199f9b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80"
				alt=""
			/>
		</div>
	</div>
</section>

<style lang="scss">
	@import '../mixins.scss';
	@import '../variables.scss';

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
