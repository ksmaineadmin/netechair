<script lang="ts">
	import Header from '$lib/header/Header.svelte';
	import '../app.scss';

	const currentYear = new Date().getFullYear();
</script>

<Header />

<main>
	<slot />
</main>

<footer>
	<p>Copyright {currentYear} New England Tech Air</p>
</footer>

<style>
	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 40px;
	}

	footer a {
		font-weight: bold;
	}

	@media (min-width: 480px) {
		footer {
			padding: 40px 0;
		}
	}
</style>
