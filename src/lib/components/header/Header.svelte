<script lang="js">
	import { page } from '$app/stores';
	import { onMount } from 'svelte';

	onMount(() => {
		let mql = window.matchMedia('(max-width: 1024px)');
		let lastScrollTop;
		const header = document.getElementById('header');
		const nav = document.getElementById('nav');
		const navToggle = document.querySelector('.mobile-nav-toggle');
		const navList = document.getElementById('primary-navigation');
		const navItems = Array.from(navList.children);

		window.addEventListener('scroll', () => {
			var scrollTop = window.pageYOffset || document.documentElement.scrollTop;
			if (scrollTop > lastScrollTop) {
				header.style.top = '-120px';
			} else {
				header.style.top = '0';
			}
			lastScrollTop = scrollTop;
		});

		navToggle.addEventListener('click', () => toggleMenu());

		navItems.forEach((item) => {
			item.addEventListener('click', () => toggleMenu());
		});

		const toggleMenu = () => {
			const visibility = nav.getAttribute('data-visible');
			if (visibility === 'false') {
				navToggle.classList.add('active');
				nav.setAttribute('data-visible', 'true');
				navToggle.setAttribute('aria-expanded', 'true');
				header.classList.add('sticky');
			} else {
				navToggle.classList.remove('active');
				nav.setAttribute('data-visible', 'false');
				navToggle.setAttribute('aria-expanded', 'false');
				header.classList.remove('sticky');
			}
		};

		// Set the appropriate data attribute based on matchMedia boolean
		if (mql) {
			nav.setAttribute('data-visible', 'false');
			navToggle.setAttribute('aria-expanded', 'false');
		} else {
			nav.setAttribute('data-visible', 'true');
			navToggle.setAttribute('aria-expanded', 'true');
		}
	});
</script>

<header id="header">
	<div class="logo-holder">
		<a href="/" aria-label="Back to the homepage">
			<svg
				version="1.1"
				xmlns="http://www.w3.org/2000/svg"
				xmlns:xlink="http://www.w3.org/1999/xlink"
				x="0px"
				y="0px"
				viewBox="0 0 452.3 134.8"
				style="enable-background:new 0 0 452.3 134.8;"
				xml:space="preserve"
			>
				<g id="Letta">
					<g>
						<g>
							<path
								class="hammah"
								d="M60.3,135.1c0,0,0-0.1,0-0.1c-2.6-0.5-2.4-2.3-2.4-4.4c0.3-9.5,0.4-18.9,0.7-28.4c0.1-1.9,0.6-3.7,0.8-5.6
				c0.2-2.2,0.4-4.5,0.6-6.8c-9.8,0-19.3,0-29,0c0.3,0.4,0.4,0.7,0.6,0.9c6.3,7.1,14.1,11.6,23.4,13.3c0.9,0.2,1.4,0.5,1.4,1.5
				c0,5.8,0,11.6,0,17.4c0,0.3-0.1,0.5-0.2,1c-1.7-0.2-3.4-0.3-5.1-0.7c-22.3-4.9-37.6-17.9-45.8-39.1C3.6,79.6,2.7,75,2.2,70.4
				c-0.1-0.6-0.3-1.2-0.5-1.8c0-1,0-1.9,0-2.9c0.6-0.1,1.2-0.2,1.8-0.2c15.3,0,30.7,0,46,0c23.7,0,47.3,0,71,0c0.6,0,1.3,0.1,2,0.2
				c-1,15.5-6,29.2-17.1,40.1c-10.3,10.1-22.4,16.6-37.2,17.9c-0.1-0.5-0.1-0.9-0.1-1.3c0-5.6,0-11.2,0-16.7c0-1.2,0.3-1.6,1.5-1.9
				c9.3-1.7,17.1-6.2,23.4-13.3c0.2-0.2,0.3-0.5,0.6-0.8c-9.8,0-19.4,0-29.3,0c0.2,2.4,0.1,4.8,0.6,7c1.2,4.7,1.1,9.4,1.2,14.2
				c0.1,6.9,0.3,13.8,0.5,20.7c0.1,1.9-0.2,2.4-2.1,2.9c-0.5,0.1-0.9,0.3-1.4,0.5C62.2,135.1,61.3,135.1,60.3,135.1z M41.9,75.9
				c11.6-4.3,23.5-4.4,35.6-3.2c0,0.7,0,1.4,0,2c0,2.6-1.1,3.5-3.7,3.3c-1.9-0.1-3.9-0.2-5.8-0.2c-1.3,0-2.5,0.5-2.8,1.8
				c-0.8,2.7-0.6,5.5-0.5,8.5c10.8,0,21.4,0,32.4,0c-6.9,9.5-15.9,15.1-27.1,17.3c0,5.6,0,10.9,0,16.5c14-2.1,25.8-8,35.3-18.2
				c9.6-10.2,14.5-22.5,15.7-36.5c-39.2,0-78.2,0-117.4,0C4.7,81.7,10,94.2,20,104.5c9.5,9.7,21,15.5,34.6,17.4c0-5.6,0-10.9,0-16.5
				c-11.3-2.2-20.2-8-27.2-17.5c11,0,21.6,0,32.4,0c-0.2-2.6-0.3-5.2-0.6-7.6c-0.2-1.8-1.2-2.8-3.1-2.9c-2.5-0.2-5-0.2-7.5-0.2
				c-1.6,0-3.3,0.1-4.9,0.1C42.6,77.4,42,77,41.9,75.9z"
							/>
							<path
								class="st0"
								d="M220.5,102.9c0,1.3,0,2.3,0,3.5c-0.4,0.1-0.9,0.4-1.3,0.4c-7.2,0-14.4-0.1-21.6-0.2c-6.3,0-12.6,0-18.9,0
				c-0.5,0-0.9,0-1.5-0.1c-0.1-0.6-0.2-1.2-0.2-1.7c0-17.7,0-35.3,0-53c0-1.2,0.4-1.7,1.6-1.7c13.3,0,26.5,0,39.8,0
				c0.5,0,0.9,0.1,1.5,0.1c0,1.3,0,2.4,0,3.6c-0.4,0.1-0.8,0.2-1.2,0.2c-12,0-24-0.1-36-0.1c-0.9,0-1.6,0.2-1.6,1.3
				c0,6.3,0,12.6,0,19c0,0.2,0.1,0.5,0.2,1c11.4,0,22.7,0,34.1,0c0,1.3,0,2.4,0,3.6c-0.9,0.1-1.7,0.1-2.4,0.1c-10,0-19.9,0-29.9,0
				c-0.6,0-1.2,0.1-1.8,0.2c0,7.8,0,15.5,0,23.4c0.6,0.1,1.2,0.3,1.9,0.3c11.7,0,23.5,0,35.2,0C219.1,102.8,219.7,102.9,220.5,102.9
				z"
							/>
							<path
								class="st0"
								d="M329.6,75.2c0-8.4,0-16.7,0-25c1.4,0,2.6,0,4,0c0.1,0.5,0.3,1,0.3,1.5c0,3.8-0.2,7.5-0.2,11.3
				c0,13.9,0,27.9,0,41.8c0,0.5-0.1,1-0.1,1.6c-1.4,0-2.6,0-4.1,0c0-9,0-18,0-27.2c-0.7-0.1-1.3-0.3-1.9-0.3c-12.6,0-25.1,0-37.7,0
				c-0.5,0-1,0.1-1.7,0.2c0,9.1,0,18.1,0,27.2c-1.5,0-2.7,0-4,0c0-18.8,0-37.5,0-56.4c1,0,1.7,0,2.5,0c1.4,0,1.6,0.2,1.6,1.7
				c-0.1,7.2-0.1,14.5-0.1,21.7c0,0.6,0.1,1.2,0.2,1.8C302.2,75.2,315.8,75.2,329.6,75.2z"
							/>
							<path
								class="st0"
								d="M277.8,60.5c-1.1,0.7-2.1,1.3-3.2,2c-0.4-0.4-0.7-0.8-1-1.2c-3.4-4.1-7.9-6.5-13.2-7.3
				c-5.7-0.9-11.3-0.9-16.8,1.1c-9.3,3.4-14.5,10-15.5,19.9c-0.6,5.2-0.1,10.2,2.1,14.9c2.9,6.3,7.6,10.5,14.4,12.2
				c7.3,1.9,14.5,1.8,21.5-1.6c2.7-1.3,5-3.1,6.9-5.4c0.3-0.3,0.6-0.6,0.9-1c1.2,0.7,2.3,1.4,3.6,2.2c-1.5,2.1-3.4,3.8-5.4,5.4
				c-3.7,2.8-7.9,4.3-12.5,5c-7,1.2-13.9,0.6-20.4-2.3c-8.4-3.7-13.2-10.2-14.8-19.2c-1.1-6-0.8-11.8,1.2-17.6
				c2.6-7.4,7.5-12.6,14.8-15.4c9.5-3.7,18.9-3.6,28.3,0.3c3.7,1.5,6.6,4.1,9,7.2c0.1,0.1,0.2,0.3,0.2,0.4
				C277.8,60.2,277.8,60.3,277.8,60.5z"
							/>
							<path
								class="st0"
								d="M153,54c0,17.6,0,34.9,0,52.4c-1.2,0.1-2.1,0.3-3.1,0.3c-1,0-1.3-0.7-1.3-1.6c0-16.4,0.1-32.9,0.1-49.3
				c0-1.7-0.1-1.8-1.9-1.8c-5.9,0-11.9,0-17.8,0c-0.6,0-1.1,0-1.8,0c0-1.3,0-2.5,0-3.8c15.8,0,31.5,0,47.3,0c0,1.3,0,2.4,0,3.8
				C167.4,54,160.3,54,153,54z"
							/>
						</g>
					</g>
				</g>
				<g id="Accent">
					<path
						class="st1"
						d="M443.1,78.9c1.8,1.5,3.7,2.7,5.2,4.3c2.1,2.2,2.8,5.1,2.9,8.1c0.1,4.8,0,9.7,0,14.5c0,0.2,0,0.3-0.1,0.6
		c-1.3,0-2.6,0-4.1,0c0-0.6,0-1.1,0-1.7c0-3.8,0-7.5,0-11.3c0-6.9-3.2-10.6-10-11.6c-2-0.3-4.1-0.5-6.2-0.5c-6.6-0.1-13.3,0-19.9,0
		c-1.7,0-1.9,0.1-1.9,1.8c0,7.2,0,14.4,0,21.6c0,0.5-0.1,1.1-0.1,1.7c-1.4,0-2.6,0-4,0c0-0.5-0.1-0.9-0.1-1.3c0-17.7,0-35.4,0-53.1
		c0-1.9,0.1-1.9,1.9-1.9c8.6,0,17.2,0,25.9,0c3.5,0,7,0.4,10.3,1.6c7.5,2.7,9.7,8.8,8.9,15.7c-0.6,5.2-3.4,8.9-8.2,11.1
		C443.5,78.6,443.2,78.8,443.1,78.9z M423.7,54.3c0-0.1,0-0.2,0-0.2c-4.3,0-8.6,0-12.9,0c-1.2,0-1.7,0.4-1.7,1.6
		c0,6.7,0,13.4,0,20.1c0,1.3,0.5,1.6,1.7,1.6c6.7,0,13.4,0,20.1-0.1c2.3,0,4.6-0.2,6.8-0.8c5.2-1.3,9.2-3.9,10-9.8
		c0.6-4.2-1-8.3-4.4-10.3c-2.1-1.3-4.5-2.1-7-2.1C432.2,54.2,427.9,54.3,423.7,54.3z"
					/>
					<path
						class="st1"
						d="M391.7,106.6c-1.3,0-2.6,0.1-3.7-0.1c-0.5-0.1-1.2-0.7-1.4-1.2c-2.2-4.8-4.4-9.6-6.6-14.5c-0.6-1.4-1.4-2-3-2
		c-8.8,0.1-17.6,0.1-26.4,0c-1.4,0-2,0.5-2.5,1.7c-2.2,4.9-4.5,9.8-6.8,14.7c-0.5,1.1-1.1,1.6-2.3,1.4c-1-0.1-2,0-3.1,0
		c0.2-0.5,0.3-0.8,0.4-1.1c8.4-17.9,16.8-35.8,25.2-53.6c1-2.1,3.7-2.4,5.1-0.5c0.4,0.6,0.7,1.2,1,1.8c7.8,17.3,15.6,34.6,23.5,51.8
		C391.3,105.5,391.4,105.9,391.7,106.6z M364.3,56.1c-4.7,9.8-9.2,19.2-13.7,28.8c9.1,0,17.8,0,26.9,0
		C373.1,75.3,368.8,65.9,364.3,56.1z"
					/>
					<path
						class="st1"
						d="M394,50.2c1.5,0,2.6,0,4,0c0,18.7,0,37.4,0,56.3c-1.4,0-2.6,0-4,0C394,87.7,394,69,394,50.2z"
					/>
					<path
						class="st1"
						d="M41.9,75.9c0.1,1.1,0.8,1.5,1.8,1.5c1.6,0,3.3-0.2,4.9-0.1c2.5,0,5,0,7.5,0.2c1.9,0.1,2.9,1.1,3.1,2.9
		c0.3,2.5,0.4,5,0.6,7.6c-10.8,0-21.4,0-32.4,0c7,9.5,15.9,15.2,27.2,17.5c0,5.5,0,10.9,0,16.5C41,120,29.5,114.3,20,104.5
		C10,94.2,4.7,81.7,3.5,67.3c39.2,0,78.2,0,117.4,0c-1.2,14-6.1,26.2-15.7,36.5C95.7,114,83.9,119.8,69.9,122c0-5.6,0-10.9,0-16.5
		c11.2-2.3,20.2-7.9,27.1-17.3c-10.9,0-21.6,0-32.4,0c-0.1-2.9-0.3-5.7,0.5-8.5c0.4-1.3,1.5-1.9,2.8-1.8c1.9,0,3.9,0.1,5.8,0.2
		c2.6,0.2,3.7-0.7,3.7-3.3c0-0.6,0-1.3,0-2C65.4,71.6,53.5,71.6,41.9,75.9z"
					/>
					<path
						class="st1"
						d="M68.2,60.2c-4,0-7.8,0-11.9,0c0-12.8,0-25.6,0-38.5c-9.9,1.9-18.4,5.7-25,12.9C24.7,41.8,21,50.4,19.8,60.2
		c-5.4,0-10.7,0-16.3,0C5,41.5,13.4,26.8,28.3,15.7C45.7,2.9,73.2,1.1,92.5,13.3c17.1,10.9,26.9,26.3,28.5,46.9
		c-5.5,0-10.8,0-16.3,0c-1.5-14.2-8.3-25.1-20.2-32.7c-4.9-3.1-10.2-4.9-16.1-5.8C68.2,34.7,68.2,47.4,68.2,60.2z"
					/>
				</g>
			</svg>
		</a>
	</div>

	<div class="righthead">
		<button
			class="hamburger mobile-nav-toggle"
			aria-controls="primary-navigation"
			aria-expanded="false"
		>
			<span class="sr-only">Menu</span>
			<span class="hamburger-line hamburger-line-1" />
			<span class="hamburger-line hamburger-line-2" />
			<span class="hamburger-line hamburger-line-3" />
		</button>
		<nav id="nav" data-visible="false">
			<ul id="primary-navigation" class="primary-navigation">
				<li>
					<a class:active={$page.url.pathname === '/'} sveltekit:prefetch href="/">Home</a>
				</li>
				<li>
					<a class:active={$page.url.pathname.includes('/team')} sveltekit:prefetch href="/team"
						>Team</a
					>
				</li>
				<li>
					<a
						class:active={$page.url.pathname.includes('/projects')}
						sveltekit:prefetch
						href="/projects">Projects</a
					>
				</li>
				<li>
					<a class:active={$page.url.pathname === '/contact'} sveltekit:prefetch href="/contact"
						>Contact</a
					>
				</li>
			</ul>
		</nav>
	</div>
</header>

<style lang="scss">
	@import '../../../variables.scss';
	@import '../../../mixins.scss';

	header {
		display: flex;
		justify-content: space-between;
		padding: 0 30px;
		align-items: center;
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		transition: 0.5s;
		z-index: 20;
		background-color: var(--surface-color);
		box-shadow: 0 3px 6px rgba(0, 0, 0, 0.16), 0 3px 6px rgba(0, 0, 0, 0.23);

		.righthead {
			display: flex;
			align-items: center;
			.rondedbutt {
				margin-left: 10px;
				background-color: var(--primary-color);
				color: var(--pure-white);
				border-radius: 90px;
				padding: 5px 20px;
			}
		}
	}

	.mobile-nav-toggle {
		display: none;
	}

	.logo-holder {
		svg {
			width: 300px;
			padding: 15px 15px 15px 0;
			.st0 {
				fill: var(--secondary-font-color);
			}
			.st1 {
				fill: var(--accent-color);
			}
			.hammah {
				fill: transparent;
			}

			@media (max-width: $device-medium) {
				width: 200px;
			}

			@media (max-width: $device-small) {
				width: 150px;
			}
		}
	}
	nav {
		font-family: var(--font-oswald);
		font-display: swap;
		font-size: 1.5rem;
		text-transform: uppercase;
		letter-spacing: 1px;

		.primary-navigation {
			list-style: none;
			display: flex;
			margin: 0;
			padding: 0;

			li {
				display: inline;
				padding: 0 1rem;
			}
		}

		a {
			color: var(--pure-white);
			&:hover {
				color: var(--accent-color);
			}
			&.active {
				color: var(--accent-color);
			}
		}
	}

	@media (max-width: $device-medium) {
		.mobile-nav-toggle {
			position: absolute;
			display: block;
			top: 1rem;
			right: 1rem;
			z-index: 9999;
			cursor: pointer;
		}

		nav[data-visible='false'] {
			transform: translateX(100%);
			transition: transform 350ms ease-out;
		}

		nav {
			position: fixed;
			inset: 0 0 0 45%;
			transform: translateX(0);
			transition: transform 350ms ease-out;
			@include supports-backdrop-filter();
			z-index: 20;
			padding: min(10vh, 10rem) 2rem;

			.primary-navigation {
				display: flex;
				flex-direction: column;

				li {
					padding: 1.5rem 0;

					a {
						font-size: clamp(1rem, 3rem, 1.5rem);
					}
				}
			}
		}
	}

	.sticky[data-visible='true'] {
		position: fixed;
		top: 0;
		width: 100%;
		z-index: 9999;
		@include supports-backdrop-filter();
	}
</style>
