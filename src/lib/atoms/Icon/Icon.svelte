<script>
	export let name;

	let getIcon = import(`../../icons/${name}Icon.svelte`);
</script>

{#await getIcon then { default: Icon }}
	<svelte:component this={Icon} />
{/await}
