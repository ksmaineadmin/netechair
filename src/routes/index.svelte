<script context="module" lang="ts">
	export const prerender = true;
</script>

<script lang="js">
	import HomepageSlider from '$lib/components/homepage-slider/homepage-slider.svelte';
	import ServicesSection from '$lib/components/services-section/services-section.svelte';
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<HomepageSlider />
<ServicesSection />

<style>
</style>
