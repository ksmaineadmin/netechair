<script context="module" lang="ts">
	// since there's no dynamic data here, we can prerender
	// it so that it gets served as a static asset in prod
	export const prerender = true;
</script>

<script lang="ts">
	import Header from '$lib/components/header/Header.svelte';
	import '../app.scss';
	import { onMount } from 'svelte';
	import AOS from 'aos';

	const currentYear = new Date().getFullYear();

	onMount(() => {
		if (typeof window !== 'undefined') {
			AOS.init();
		}
	});
</script>

<Header />

<main>
	<slot />
</main>

<footer>
	<p>Copyright {currentYear} New England Tech Air</p>
</footer>

<style lang="scss">
	main {
		height: 100%;
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 40px;

		p {
			color: var(--secondary-font-color);
		}
	}

	@media (min-width: 480px) {
		footer {
			padding: 40px 0;
		}
	}
</style>
