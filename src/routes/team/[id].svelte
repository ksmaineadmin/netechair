<script context="module" lang="js">
	export async function load({ fetch, params }) {
		let id = params.id;
		const res = await fetch(`https://jsonplaceholder.typicode.com/users/${id}`);
		const data = await res.json();
		if (res.ok) {
			return {
				props: { employee: data }
			};
		}
	}
</script>

<script lang="js">
	export let employee;
</script>

<h1>{employee.name}</h1>
<ul>
	<li>{employee.email}</li>
	<li>{employee.phone}</li>
</ul>

<a href="/team">Go back</a>
