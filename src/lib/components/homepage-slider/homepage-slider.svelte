<script lang="js">
	import { onMount } from 'svelte';
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
		<source
			src="https://vectorform.com/wp-content/themes/vectorform/videos/about.mp4"
			type="video/mp4"
		/>
		<source
			src="https://vectorform.com/wp-content/themes/vectorform/videos/about.webm"
			type="video/webm"
		/>
		<source
			src="https://vectorform.com/wp-content/themes/vectorform/videos/about.ogv"
			type="video/ogv"
		/>
	</video>
	<div class="overlay">
		<div class="overlay__inner">
			<h1>In Business for Over Thirty Five Years</h1>
		</div>
	</div>
</div>

<style lang="scss">
	#video-container {
		position: relative;
		width: 100%;
		height: 100%;
		z-index: 10;

		.touch & {
			background: url(http://xtianmiller.com/dist/videos/winter_creek.jpg) no-repeat center;
			background-size: cover;
		}
	}
	video {
		width: 100%;
		height: 100%;

		.touch & {
			display: none;
		}
	}

	.overlay {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		z-index: 20;
		background-color: rgba(0, 0, 0, 0.7);
		padding-left: 6%;
		padding-right: 6%;
		display: table;

		&__inner {
			width: 100%;
			height: auto;
			display: table-cell;
			vertical-align: middle;
			text-align: center;
		}

		h1,
		h2 {
			max-width: 40em;
			font-weight: 700;
			color: #fff;
			font-family: 'Raleway', sans-serif;
			line-height: 1.3;
			margin: 0 auto;
		}

		p {
			padding-top: 1em;
			max-width: 40em;
			margin: 0 auto;
		}

		a.btn {
			display: inline-block;
			margin-top: 25px;
			border: 1px solid #00c1bb;
			color: #00c1bb;
			text-decoration: none;
			font-size: 14px;
			text-transform: uppercase;
			letter-spacing: 2px;
			position: relative;
			overflow: hidden;
		}

		a.btn span {
			display: inline-block;
			padding: 6px 40px;
			transition: transform 0.4s;
		}

		a.btn .row2 {
			position: absolute;
			left: 0;
			top: 0;
			transform: translateY(100%);
		}

		a.btn:hover .row1 {
			transform: translateY(-100%);
		}

		a.btn:hover .row2 {
			transform: translateY(0);
		}
	}
</style>
