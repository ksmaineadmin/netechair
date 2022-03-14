<section>
	<div class="affiliations__container">
		<div data-aos="fade-up" data-aos-delay="0">
			<img src="images/abc_thumb-150x109-1.png" alt="ABC Industries Logo" data-aos="fade-up" />
		</div>
		<div data-aos="fade-up" data-aos-delay="100">
			<img src="images/ashrae_thumb-150x109-1.png" alt="ASHRAE Professional association logo" />
		</div>
		<div data-aos="fade-up" data-aos-delay="200">
			<img src="images/osha_thumb-150x109-1.png" alt="OSHA logo" />
		</div>
		<div data-aos="fade-up" data-aos-delay="300">
			<img src="images/smacna_thumb-150x109.png" alt="SMACNA Logo" />
		</div>
	</div>
</section>

<style lang="scss">
	@import '../../../variables.scss';

	section {
		display: grid;
		grid-template-columns: 1fr;
		gap: 1rem;
		align-items: center;
		padding: 4rem 10rem;
		min-height: 50vh;
		background-color: var(--surface-color);
	}
	@media screen and (max-width: $device-medium) {
		section {
			padding: 1rem 1rem;
			gap: 1rem;
		}
	}

	.affiliations {
		&__container {
			display: grid;
			grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
			justify-content: center;
			justify-items: center;
			gap: 3rem;

			img {
				filter: grayscale(100);
				transition: filter ease-in-out 200ms;

				&:hover {
					filter: grayscale(0);
				}
			}
		}
	}
</style>
