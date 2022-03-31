<script lang="js">
	export let title = '';
	export let backgroundImageUrl = '';
</script>

<div
	class="hero__container"
	style="background-image: linear-gradient(rgba(0, 0, 0, 0.9), rgba(9, 9, 9, 0.7)), url({backgroundImageUrl})"
>
	<h1 class="hero__title">{title}</h1>
</div>

<style lang="scss">
	@import '../../../mixins.scss';
	@import '../../../variables.scss';

	.hero {
		&__container {
			margin-top: 120px;
			min-height: 400px;
			display: flex;
			align-items: center;
			justify-content: center;
			background-color: #000000;
			background-position: center;
			background-size: cover;
			background-repeat: no-repeat;
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
</style>
