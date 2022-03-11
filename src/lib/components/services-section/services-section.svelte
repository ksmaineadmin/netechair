<script></script>

<section>
	<article>
		<span>Icon here</span>
		<h3>Our services</h3>
		<p>
			We draw on expertise from across the entire project scope, including engineering, procurement,
			fabrication, construction, 3D coordination and installation.
		</p>
		<p>Our comprehensive services have transformed project execution.</p>
		<a href="request-pricing">Request pricing</a>
	</article>

	<article>
		<span>Icon here</span>
		<h3>Our services</h3>
		<p>
			We draw on expertise from across the entire project scope, including engineering, procurement,
			fabrication, construction, 3D coordination and installation.
		</p>
		<p>Our comprehensive services have transformed project execution.</p>
		<a href="request-pricing">Request pricing</a>
	</article>

	<article>
		<span>Icon here</span>
		<h3>Our services</h3>
		<p>
			We draw on expertise from across the entire project scope, including engineering, procurement,
			fabrication, construction, 3D coordination and installation.
		</p>
		<p>Our comprehensive services have transformed project execution.</p>
		<a href="request-pricing">Request pricing</a>
	</article>
</section>

<style lang="scss">
	section {
		background: var(--accent-color-light);
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
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

		&:hover {
			cursor: pointer;
			border-bottom: 4px solid var(--accent-color);
		}
	}

	.span-all {
		grid-column: 1/-1;
	}
</style>
