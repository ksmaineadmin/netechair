<script lang="js">
	import { onMount } from 'svelte';
	import SlickButton from '../slick-button/slick-button.svelte';

	onMount(() => {
		function debounce(func, wait, immediate) {
			// Debounce
			// http://davidwalsh.name/javascript-debounce-function

			var timeout;
			return function () {
				var context = this,
					args = arguments;
				var later = function () {
					timeout = null;
					if (!immediate) {
						func.apply(context, args);
					}
				};
				var callNow = immediate && !timeout;
				clearTimeout(timeout);
				timeout = setTimeout(later, wait);
				if (callNow) {
					func.apply(context, args);
				}
			};
		}

		var htmlTag = document.getElementsByTagName('html')[0];
		var videoContainer = document.querySelector('#video-container');
		var videoElem = document.querySelector('#video-container video');

		var minW = 320; // Minimum video width allowed
		var vidWOrig; // Original video dimensions
		var vidHOrig;

		vidWOrig = videoElem.getAttribute('width');
		vidHOrig = videoElem.getAttribute('height');

		var videoCover = function () {
			var winWidth =
				window.innerWidth || document.documentElement.clientWidth || document.body.clientWidth;
			var winHeight =
				window.innerHeight || document.documentElement.clientHeight || document.body.clientHeight;

			// Set the video viewport to the window size

			videoContainer.style.width = winWidth + 'px';
			videoContainer.style.height = winHeight + 'px';

			// Use largest scale factor of horizontal/vertical
			var scaleH = winWidth / vidWOrig;
			var scaleV = winHeight / vidHOrig;
			var scale = scaleH > scaleV ? scaleH : scaleV;

			// Don't allow scaled width < minimum video width
			if (scale * vidWOrig < minW) {
				scale = minW / vidWOrig;
			}

			// Scale the video
			var videoNewWidth = scale * vidWOrig;
			var videoNewHeight = scale * vidHOrig;

			videoElem.style.width = videoNewWidth + 'px';
			videoElem.style.height = videoNewHeight + 'px';

			// Center it by scrolling the video viewport
			videoContainer.scrollLeft = (videoNewWidth - winWidth) / 2;
			videoContainer.scrollTop = (videoNewHeight - winHeight) / 2;
		};

		if (htmlTag.classList.contains('no-touch')) {
			videoCover();

			// Adjust on resize
			var updateVideo = debounce(function () {
				videoCover();
			}, 100);

			window.addEventListener('resize', updateVideo);
		}
	});
</script>

<div id="video-container">
	<video preload="auto" autoplay loop muted width="1440" height="810">
		<source src="homepage-videos/oil-pipes.mp4" type="video/mp4" />
	</video>
	<div class="overlay">
		<h1>In Business for Over Thirty Five Years</h1>
		<SlickButton />
	</div>
</div>

<style lang="scss">
	@import '../../../variables.scss';

	#video-container {
		display: grid;
		align-items: center;
		position: relative;
		height: 100%;
		z-index: 10;

		.touch & {
			background: url(http://xtianmiller.com/dist/videos/winter_creek.jpg) no-repeat center;
			background-size: cover;
		}

		&::before {
			content: '';
			background: rgba(0, 0, 0, 0.6);
			position: absolute;
			inset: 0;
		}
	}
	video {
		width: 100%;
		height: 100%;
		display: block;
		object-fit: cover;
		height: calc(100vh - 100px);

		.touch & {
			display: none;
		}
	}

	.overlay {
		position: absolute;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		width: 100%;
		z-index: 20;

		h1,
		h2 {
			max-width: 30rem;
			font-weight: 700;
			color: #fff;
			font-family: 'Raleway', sans-serif;
			line-height: 1.3;
		}

		a {
			background: white;
			border-radius: 90px;
			padding: 5px 20px;
			width: 100%;
			text-align: center;
			font-size: 1.5rem;
			color: black;
		}
	}
</style>
