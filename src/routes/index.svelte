<script context="module" lang="ts">
	// since there's no dynamic data here, we can prerender
	// it so that it gets served as a static asset in prod
	export const prerender = true;
</script>

<script lang="js">
	import HomepageSlider from '$lib/components/homepage-slider/homepage-slider.svelte';
	import ServicesSection from '$lib/components/services-section/services-section.svelte';
	import Affiliations from '../lib/components/affiliations/affiliations.svelte';
	import Testimonials from '../lib/components/testimonials/testimonials.svelte';
	import Capabilities from '../lib/components/capabilities/capabilities.svelte';
</script>

<svelte:head>
	<title>Tech Air - HVAC, Duct Construction</title>
</svelte:head>

<HomepageSlider />
<ServicesSection />
<Capabilities />
<Testimonials />
<Affiliations />
