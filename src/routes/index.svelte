<script context="module" lang="ts">
	// since there's no dynamic data here, we can prerender
	// it so that it gets served as a static asset in prod
	export const prerender = true;
</script>

<script lang="js">
	import HomepageSlider from '$lib/components/homepage-slider/homepage-slider.svelte';
	import ServicesSection from '$lib/components/services-section/services-section.svelte';
	import Affiliations from '../lib/components/affiliations/affiliations.svelte';
	import CountUp from '../lib/components/count-up/count-up.svelte';
</script>

<svelte:head>
	<title>New England Tech Air - HVAC, Duct Construction</title>
</svelte:head>

<HomepageSlider />
<ServicesSection />

<section class="counter__container">
	<CountUp countMax="2000000" description="LBS of Duct a Year!" data-aos="fade-up">
		<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" slot="icon">
			<path
				d="M64 400C64 408.8 71.16 416 80 416H480C497.7 416 512 430.3 512 448C512 465.7 497.7 480 480 480H80C35.82 480 0 444.2 0 400V64C0 46.33 14.33 32 32 32C49.67 32 64 46.33 64 64V400zM342.6 278.6C330.1 291.1 309.9 291.1 297.4 278.6L240 221.3L150.6 310.6C138.1 323.1 117.9 323.1 105.4 310.6C92.88 298.1 92.88 277.9 105.4 265.4L217.4 153.4C229.9 140.9 250.1 140.9 262.6 153.4L320 210.7L425.4 105.4C437.9 92.88 458.1 92.88 470.6 105.4C483.1 117.9 483.1 138.1 470.6 150.6L342.6 278.6z"
			/></svg
		>
	</CountUp>
	<CountUp countMax="100000" description="Square Foot Facility">
		<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 384 512" slot="icon"
			><path
				d="M336 0C362.5 0 384 21.49 384 48V464C384 490.5 362.5 512 336 512H240V432C240 405.5 218.5 384 192 384C165.5 384 144 405.5 144 432V512H48C21.49 512 0 490.5 0 464V48C0 21.49 21.49 0 48 0H336zM64 272C64 280.8 71.16 288 80 288H112C120.8 288 128 280.8 128 272V240C128 231.2 120.8 224 112 224H80C71.16 224 64 231.2 64 240V272zM176 224C167.2 224 160 231.2 160 240V272C160 280.8 167.2 288 176 288H208C216.8 288 224 280.8 224 272V240C224 231.2 216.8 224 208 224H176zM256 272C256 280.8 263.2 288 272 288H304C312.8 288 320 280.8 320 272V240C320 231.2 312.8 224 304 224H272C263.2 224 256 231.2 256 240V272zM80 96C71.16 96 64 103.2 64 112V144C64 152.8 71.16 160 80 160H112C120.8 160 128 152.8 128 144V112C128 103.2 120.8 96 112 96H80zM160 144C160 152.8 167.2 160 176 160H208C216.8 160 224 152.8 224 144V112C224 103.2 216.8 96 208 96H176C167.2 96 160 103.2 160 112V144zM272 96C263.2 96 256 103.2 256 112V144C256 152.8 263.2 160 272 160H304C312.8 160 320 152.8 320 144V112C320 103.2 312.8 96 304 96H272z"
			/></svg
		>
	</CountUp>
	<CountUp countMax="20" description="States worked in">
		<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512" slot="icon">
			<path
				d="M544 61.63V30.74c0-25-28.81-37.99-53.17-26.49C306.3 91.5 321.5-62.25 96 32.38V32c0-17.75-14.25-32-32-32S32 14.25 32 32L31.96 496c0 8.75 7.25 16 15.1 16H80C88.75 512 96 504.8 96 496V384c200-92.25 238.8 53.25 428.1-23.12C536.3 355.9 544 344.4 544 332.1V296.1c-46.98 17.25-86.42 24.12-120.8 24.12c-40.25-.125-74.17-8.5-107.7-16.62C254 288.5 195.3 274.8 96 314.8v-34.5c102-37.63 166.5-22.75 228.4-7.625C385.1 287.8 444.7 301.4 544 261.5V200c-46.98 17.25-86.42 24.12-120.8 24.12c-40.25 0-74.17-8.375-107.7-16.5C254 192.5 195.3 178.8 96 218.8v-34.5c102-37.5 166.5-22.62 228.4-7.5C385.1 191.8 444.7 205.4 544 165.6V96.75c-57.75 23.5-100.4 31.38-135.8 31.38c-62.96 0-118.9-27.09-120.2-27.38V67.5C331.9 78.94 390.1 128.3 544 61.63zM160 136c-8.75 0-16-7.125-16-16s7.25-16 16-16s16 7.125 16 16S168.8 136 160 136zM160 72c-8.75 0-16-7-16-16c0-8.75 7.25-16 16-16s16 7.125 16 16S168.8 72 160 72zM224 128C215.3 128 208 120.9 208 112S215.3 96 224 96s16 7 16 16C240 120.8 232.8 128 224 128zM224 64.25c-8.75 0-16-7-16-16c0-8.75 7.25-16 16-16s16 7.125 16 16S232.8 64.25 224 64.25z"
			/></svg
		>
	</CountUp>
</section>

<Affiliations />

<style lang="scss">
	.counter {
		&__container {
			display: grid;
			grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
			justify-content: space-around;
			gap: 1rem;
			align-items: center;
			padding: 4rem 10rem;
			min-height: 50vh;
			background-color: #1c1c1c;
			background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 2000 1500'%3E%3Cdefs%3E%3CradialGradient id='a' gradientUnits='objectBoundingBox'%3E%3Cstop offset='0' stop-color='%23000000'/%3E%3Cstop offset='1' stop-color='%231C1C1C'/%3E%3C/radialGradient%3E%3ClinearGradient id='b' gradientUnits='userSpaceOnUse' x1='0' y1='750' x2='1550' y2='750'%3E%3Cstop offset='0' stop-color='%230e0e0e'/%3E%3Cstop offset='1' stop-color='%231C1C1C'/%3E%3C/linearGradient%3E%3Cpath id='s' fill='url(%23b)' d='M1549.2 51.6c-5.4 99.1-20.2 197.6-44.2 293.6c-24.1 96-57.4 189.4-99.3 278.6c-41.9 89.2-92.4 174.1-150.3 253.3c-58 79.2-123.4 152.6-195.1 219c-71.7 66.4-149.6 125.8-232.2 177.2c-82.7 51.4-170.1 94.7-260.7 129.1c-90.6 34.4-184.4 60-279.5 76.3C192.6 1495 96.1 1502 0 1500c96.1-2.1 191.8-13.3 285.4-33.6c93.6-20.2 185-49.5 272.5-87.2c87.6-37.7 171.3-83.8 249.6-137.3c78.4-53.5 151.5-114.5 217.9-181.7c66.5-67.2 126.4-140.7 178.6-218.9c52.3-78.3 96.9-161.4 133-247.9c36.1-86.5 63.8-176.2 82.6-267.6c18.8-91.4 28.6-184.4 29.6-277.4c0.3-27.6 23.2-48.7 50.8-48.4s49.5 21.8 49.2 49.5c0 0.7 0 1.3-0.1 2L1549.2 51.6z'/%3E%3Cg id='g'%3E%3Cuse href='%23s' transform='scale(0.12) rotate(60)'/%3E%3Cuse href='%23s' transform='scale(0.2) rotate(10)'/%3E%3Cuse href='%23s' transform='scale(0.25) rotate(40)'/%3E%3Cuse href='%23s' transform='scale(0.3) rotate(-20)'/%3E%3Cuse href='%23s' transform='scale(0.4) rotate(-30)'/%3E%3Cuse href='%23s' transform='scale(0.5) rotate(20)'/%3E%3Cuse href='%23s' transform='scale(0.6) rotate(60)'/%3E%3Cuse href='%23s' transform='scale(0.7) rotate(10)'/%3E%3Cuse href='%23s' transform='scale(0.835) rotate(-40)'/%3E%3Cuse href='%23s' transform='scale(0.9) rotate(40)'/%3E%3Cuse href='%23s' transform='scale(1.05) rotate(25)'/%3E%3Cuse href='%23s' transform='scale(1.2) rotate(8)'/%3E%3Cuse href='%23s' transform='scale(1.333) rotate(-60)'/%3E%3Cuse href='%23s' transform='scale(1.45) rotate(-30)'/%3E%3Cuse href='%23s' transform='scale(1.6) rotate(10)'/%3E%3C/g%3E%3C/defs%3E%3Cg transform='rotate(0 0 0)'%3E%3Cg transform='rotate(0 0 0)'%3E%3Ccircle fill='url(%23a)' r='3000'/%3E%3Cg opacity='0.5'%3E%3Ccircle fill='url(%23a)' r='2000'/%3E%3Ccircle fill='url(%23a)' r='1800'/%3E%3Ccircle fill='url(%23a)' r='1700'/%3E%3Ccircle fill='url(%23a)' r='1651'/%3E%3Ccircle fill='url(%23a)' r='1450'/%3E%3Ccircle fill='url(%23a)' r='1250'/%3E%3Ccircle fill='url(%23a)' r='1175'/%3E%3Ccircle fill='url(%23a)' r='900'/%3E%3Ccircle fill='url(%23a)' r='750'/%3E%3Ccircle fill='url(%23a)' r='500'/%3E%3Ccircle fill='url(%23a)' r='380'/%3E%3Ccircle fill='url(%23a)' r='250'/%3E%3C/g%3E%3Cg transform='rotate(0 0 0)'%3E%3Cuse href='%23g' transform='rotate(10)'/%3E%3Cuse href='%23g' transform='rotate(120)'/%3E%3Cuse href='%23g' transform='rotate(240)'/%3E%3C/g%3E%3Ccircle fill-opacity='0.71' fill='url(%23a)' r='3000'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
			background-attachment: fixed;
			background-size: cover;
		}
	}
</style>
