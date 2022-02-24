<script context="module" lang="js">
    export async function load({fetch, props}) {
        const res = await fetch('https://jsonplaceholder.typicode.com/users')
        const data = await res.json();
        let formattedData = data.map((val) => {
            return {
                ...val,
                id: val.name.replace(" ", "-").toLowerCase()
            }
        })
        if (res.ok) {
            return {
                props: {team: formattedData}
            }
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