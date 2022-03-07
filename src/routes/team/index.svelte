<script context="module" lang="js">
	export async function load({ fetch }) {
		const res = await fetch('https://jsonplaceholder.typicode.com/users');
		const data = await res.json();
		if (res.ok) {
			return {
				props: { team: data }
			};
		}
	}
</script>

<script lang="js">
	export let team;
</script>

<h1>Team</h1>

{#each team as person}
	<a href={`/team/${person.id}`}>
		{person.name}
	</a>
{/each}
