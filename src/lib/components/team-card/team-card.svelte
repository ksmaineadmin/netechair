<script lang="js">
	export let employeeName;
	export let title;
</script>

<div class="card">
	<p class="profile-name">{employeeName}</p>
	<p class="profile-title">{title}</p>
</div>

<style lang="scss">
	.card {
		background: var(--surface-color);
		width: 100%;
		color: white;
		border-radius: 4px;
		text-align: center;
		padding: 1rem;
		box-shadow: 0 8px 6px -6px black;
		.profile-name {
			font-weight: 500;
			font-size: 1.3rem;
			margin: 0px;
		}
		.profile-title {
			font-weight: 100;
			margin: 0px;
			color: var(--accent-color);
		}
	}
</style>
