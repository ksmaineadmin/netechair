<script lang="js">
	import { onMount } from 'svelte';

	onMount(() => {});
</script>

<section>
	<div class="hero__container">
		<h1 class="hero__title">Portfolio Item Title</h1>
	</div>
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
		</div>
		<div class="portfolio__gallery">
			Images here
			<img src="" />
			<img src="" />
			<img src="" />
		</div>
	</div>
</section>

<style lang="scss">
	@import '../mixins.scss';
	@import '../variables.scss';

	.hero {
		&__container {
			display: flex;
			align-items: center;
			justify-content: center;
			background-color: #000000;
			background-position: center;
			background-size: cover;
			background-repeat: no-repeat;
			min-height: 300px;
			background-image: linear-gradient(rgba(0, 0, 0, 0.9), rgba(9, 9, 9, 0.4)),
				url('images/sparks.jpg');
			background-position: 50%;
			background-size: cover;
			background-attachment: fixed;
		}

		&__title {
			--shadow-color: -20deg 0% 0%;
			--shadow-elevation-medium: 0.3px 0.5px 0.7px hsl(var(--shadow-color) / 0.36),
				0.8px 1.6px 2px hsl(var(--shadow-color) / 0.36),
				2.1px 4.1px 5.2px hsl(var(--shadow-color) / 0.36),
				5px 10px 12.6px hsl(var(--shadow-color) / 0.36);
			text-shadow: var(--shadow-elevation-medium);
			@include section-header();
			color: var(--pure-white);
		}
	}

	.portfolio {
		&__container {
			max-width: $device-large;
			margin: 0 auto;
			display: grid;
			grid-template-columns: 4fr 8fr;
			gap: 1rem;
			justify-content: center;
		}
		&__title {
			margin-bottom: 2rem;
			font-size: 1.5rem;
		}
	}
</style>
