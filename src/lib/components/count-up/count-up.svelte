<script>
	import { onMount } from 'svelte';
	export let countMax;
	export let description;
	let currentCounter;

	onMount(() => {
		let ioOptions = {
			root: null,
			rootMargin: '0px',
			threshold: 1.0
		};

		let onObserved = (entries, observer) => {
			entries.forEach((e) => {
				if (e.isIntersecting) {
					countIni();
				}
			});
		};

		let observer = new IntersectionObserver(onObserved, ioOptions);
		let target = currentCounter;
		observer.observe(target);

		let startNum = 0,
			nSecond = 2,
			resolutionMS = 33,
			deltaNum = (countMax - startNum) / (1000 / resolutionMS) / nSecond;

		function countIni() {
			var handle = setInterval(() => {
				var x = startNum.toLocaleString(undefined, {
					minimumFractionDigits: 0,
					maximumFractionDigits: 0
				});
				currentCounter.innerText = x.toString();

				if (startNum >= countMax) clearInterval(handle);

				startNum += deltaNum;
				startNum = Math.min(startNum, countMax);
			}, resolutionMS);
		}
	});
</script>

<div class="count__container" data-aos="fade-up">
	<div class="count__icon">
		<slot name="icon" />
	</div>
	<div class="count__number" bind:this={currentCounter}>0</div>
	<p class="count__description">{description}</p>
</div>

<style lang="scss">
	.count {
		&__container {
			display: grid;
			grid-template-columns: 1fr;
			gap: 1rem;
			justify-content: center;
			justify-items: center;
		}
		// Ignore the red squiggles, weird issue with svelteKit and SCSS combined with the :global modifier
		&__icon {
			:global(> :first-child) {
				width: 100%;
				height: 56px;
				fill: transparent;
				stroke: var(--accent-color);
				stroke-width: 1rem;
			}
		}

		&__number {
			min-width: 140px;
			border-radius: 8px;
			font-size: 3rem;
			color: var(--accent-color);
			text-align: center;
		}
	}
</style>
