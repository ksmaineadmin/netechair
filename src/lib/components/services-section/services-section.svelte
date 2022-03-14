<script context="module" lang="ts">
	export const prerender = true;
</script>

<script>
	import SlickButton from '../slick-button/slick-button.svelte';
</script>

<section>
	<article>
		<div data-aos="fade-up" data-aos-delay="100" class="article__inner">
			<img src="images/home/undraw_at_work_re_qotl.svg" alt="" />
			<h3>Our services</h3>
			<p>
				We draw on expertise from across the entire project scope, including engineering,
				procurement, fabrication, construction, 3D coordination and installation. Our comprehensive
				services have transformed project execution.
			</p>
			<a href="request-pricing">Request pricing</a>
		</div>
	</article>

	<article>
		<div data-aos="fade-up" data-aos-delay="200" class="article__inner">
			<img src="images/home/undraw_features_overview.svg" alt="" />
			<h3>Featured Projects</h3>
			<p>
				We've given our clients the confidence that we can deliver complex, logistically
				challenging, and technically difficult projects on time while maintaining safety as our #1
				priority.
			</p>
			<a href="request-pricing">Request pricing</a>
		</div>
	</article>

	<article>
		<div data-aos="fade-up" data-aos-delay="300" class="article__inner">
			<img src="images/home/undraw_career_development.svg" alt="" />
			<h3>New Careers</h3>
			<p>
				Tech Air the leader in innovation and employment growth within the HVAC industry. We design
				and build challenging and unique projects that are re-shaping the landscape of New England.
				Come build a better future with us.
			</p>
			<a href="request-pricing">Request pricing</a>
		</div>
	</article>
</section>

<style lang="scss">
	@import '../../../variables.scss';

	section {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
		gap: 1rem;
		padding: 2rem 10rem;
	}

	@media screen and (max-width: $device-medium) {
		section {
			padding: 1rem 1rem;
			gap: 1rem;
		}

		article {
			width: 100%;
		}
	}

	article {
		background: var(--surface-color);
		border-radius: 8px;
		padding: 2rem;
		text-align: center;
		border-bottom: 4px solid transparent;
		transition: border-bottom ease-in 100ms;

		.article__inner {
			display: grid;
			grid-template-columns: 1fr;
			grid-template-rows: auto auto 1fr auto;
			height: 100%;
		}

		img {
			width: 100%;
			max-height: 120px;
		}

		h3 {
			font-size: 1.5rem;
			color: var(--pure-white);
		}

		p {
			color: var(--secondary-font-color);
		}

		&:hover {
			border-bottom: 4px solid var(--accent-color);
		}
	}

	.span-all {
		grid-column: 1/-1;
	}
</style>
