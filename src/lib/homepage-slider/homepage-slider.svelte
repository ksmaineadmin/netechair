<script lang="js">
	import { onMount } from 'svelte';
	onMount(() => {
		const slideArray = [];
		for (let i = 0; i < document.querySelectorAll('.slider div').length; i++) {
			slideArray.push(document.querySelectorAll('.slider div')[i].dataset.background);
		}

		let currentSlideIndex = -1;

		function advanceSliderItem() {
			currentSlideIndex++;

			if (currentSlideIndex >= slideArray.length) {
				currentSlideIndex = 0;
			}

			document.querySelector('.slider').style.cssText =
				'background: url("' +
				slideArray[currentSlideIndex] +
				'") no-repeat center center; background-size: cover;';

			const elems = document.getElementsByClassName('caption');
			for (let i = 0; i < elems.length; i++) {
				elems[i].style.cssText = 'opacity: 0;';
			}

			// const currentCaption = document.querySelector('.caption-' + currentSlideIndex);
			// currentCaption.style.cssText = 'opacity: 1;';
		}

		let intervalID = setInterval(advanceSliderItem, 5000);
	});
</script>

<div class="slider">
	<div
		class="slide"
		data-background="https://images.unsplash.com/photo-1504917595217-d4dc5ebe6122?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80"
	/>
	<!-- <p class="caption caption-0">
		The first slide.
		<br /><small>This is an awesome forest.</small>
	</p> -->

	<div
		class="slide"
		data-background="https://images.unsplash.com/photo-1620203853151-496c7228306c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1896&q=80"
	/>

	<div
		class="slide"
		data-background="https://images.unsplash.com/photo-1541888946425-d81bb19240f5?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80"
	/>
</div>

<style>
	.slider {
		position: relative;
		overflow: hidden;
		width: 100%;
		height: 100vh;
		margin: 0 auto;
		background-size: cover;
		border-radius: 3px;
		transition: background-image 0.8s ease-in-out;
	}

	.slider .slide {
		display: none;
	}

	.caption {
		position: absolute;
		right: 0;
		top: 0;
		bottom: 0;
		opacity: 0;
		display: inline-block;
		padding: 48px;
		background: rgba(0, 0, 0, 0.75);
		color: white;
		margin: 0;
		font-size: 24px;
		font-weight: 700;
		transition: all 0.8s ease-in-out;
	}

	.caption small {
		font-size: 16px;
		font-weight: 400;
	}
</style>
