<script lang="js">
	export let buttonLink;
	export let buttonName;
</script>

<div class="button-container">
	<div class="center">
		<a href={buttonLink}>
			<button class="btn">
				<svg width="180px" height="60px" viewBox="0 0 180 60" class="border">
					<polyline points="179,1 179,59 1,59 1,1 179,1" class="bg-line" />
					<polyline points="179,1 179,59 1,59 1,1 179,1" class="hl-line" />
				</svg>
				<span>{buttonName}</span>
			</button>
		</a>
	</div>
</div>

<style lang="scss">
	.button-container {
		margin-top: 1rem;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.center {
		width: 180px;
		height: 60px;
		position: absolute;
	}

	.btn {
		width: 180px;
		height: 60px;
		cursor: pointer;
		background: rgba(0, 0, 0, 0.3);
		border: 1px solid var(--accent-color);
		outline: none;
		transition: 1s ease-in-out;
	}

	svg {
		position: absolute;
		left: 0;
		top: 0;
		fill: none;
		stroke: #fff;
		stroke-dasharray: 150 480;
		stroke-dashoffset: 150;
		transition: 1s ease-in-out;
	}

	.btn:hover {
		transition: 1s ease-in-out;
		background: var(--accent-color);
	}

	.btn:hover svg {
		stroke-dashoffset: -480;
	}

	.btn span {
		color: white;
		font-size: 18px;
		font-weight: 100;
	}
</style>
