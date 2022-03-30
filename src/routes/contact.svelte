<script context="module">
	export const prerender = true;
</script>

<svelte:head>
	<title>Tech Air - Contact</title>
</svelte:head>

<section>
	<div class="content">
		<h1 data-aos="fade-up" class="page-header">Contact</h1>

		<p class="introlang" data-aos="fade-up">
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusantium ad quidem deleniti
			quaerat, aliquam ullam laboriosam tempora beatae, accusamus autem laborum. Magnam neque
			pariatur illo porro doloremque velit sequi illum.
		</p>
		<form name="contact" netlify>
			<p data-aos="fade-up">
				<label for="name">Name</label><input type="text" name="name" id="name" />
			</p>
			<p data-aos="fade-up">
				<label for="email">Email</label><input type="email" name="email" />
			</p>
			<p data-aos="fade-up">
				<label for="subject">Subject</label><input type="text" name="subject" />
			</p>
			<p data-aos="fade-up">
				<label for="details">Details</label><textarea name="details" rows="7" />
			</p>
			<p data-aos="fade-up">
				<label for="file">Add File</label>
				<input name="file" type="file" />
			</p>

			<p data-aos="fade-up">
				<button class="submit" type="submit">Submit</button>
			</p>
		</form>
	</div>
</section>

<style lang="scss">
	@import '../mixins.scss';

	section {
		padding: 1rem 10rem;
	}

	.page-header {
		@include section-header();
		margin: 0;
	}
	.content {
		max-width: 900px;
		width: 100%;
		padding: 0 15px;
		margin: 0 auto 50px;
		.introlang {
			color: var(--secondary-font-color);
			margin-bottom: 60px;
			font-size: 18px;
			line-height: 35px;
		}
		form {
			display: flex;
			flex-direction: column;
			max-width: 700px;
			margin: 0 auto;
			p {
				display: flex;
				flex-direction: column;
			}
			p:last-child {
				align-items: center;
			}
			input,
			textarea {
				border: none;
				padding: 16px 10px 10px 10px;
				font-size: 17px;
				background-color: var(--surface-color);
				color: #fff;
				border-bottom: 6px solid var(--surface-color);
				line-height: 30px;
				&:focus {
					border-bottom: 6px solid var(--accent-color);
					outline: none;
				}
			}
			button.submit {
				border-radius: 0;
				padding: 10px;
				// font-weight: 900;
				text-transform: uppercase;
				font-size: 18px;
				letter-spacing: 0.6px;
				width: 200px;
				color: var(--accent-color);
				border: 1px solid var(--accent-color);
				background-color: transparent;
				cursor: pointer;
				transition: all 300ms cubic-bezier(0.19, 1, 0.22, 1);
				&:hover {
					background-color: var(--accent-color);
					color: var(--background-color);
					transition: all 300ms cubic-bezier(0.19, 1, 0.22, 1);
				}
			}
		}
	}
</style>
