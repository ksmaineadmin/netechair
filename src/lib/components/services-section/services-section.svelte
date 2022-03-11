<script context="module" lang="ts">
	export const prerender = true;
</script>

<section>
	<article>
		<div data-aos="fade-up" data-aos-delay="100">
			<span>Icon here</span>
			<h3>Our services</h3>
			<p>
				We draw on expertise from across the entire project scope, including engineering,
				procurement, fabrication, construction, 3D coordination and installation.
			</p>
			<p>Our comprehensive services have transformed project execution.</p>
			<a href="request-pricing">Request pricing</a>
		</div>
	</article>

	<article>
		<div data-aos="fade-up" data-aos-delay="200">
			<span>Icon here</span>
			<h3>Featured Projects</h3>
			<p>
				We’ve given our clients the confidence that we can deliver complex, logistically
				challenging, and technically difficult projects on time while maintaining safety as our #1
				priority.
			</p>
			<a href="request-pricing">Request pricing</a>
		</div>
	</article>

	<article>
		<div data-aos="fade-up" data-aos-delay="300">
			<span>Icon here</span>
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
	section {
		background: var(--accent-color-light);
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 1rem;
		padding: 2rem 10rem;
	}

	article {
		background: var(--card-surface-color);
		border-radius: 2px;
		padding: 2rem;
		text-align: center;
		border-bottom: 4px solid transparent;
		transition: border-bottom ease-in 100ms;

		h3 {
			font-size: 1.5rem;
		}

		&:hover {
			border-bottom: 4px solid var(--accent-color);
		}
	}

	.span-all {
		grid-column: 1/-1;
	}
</style>
