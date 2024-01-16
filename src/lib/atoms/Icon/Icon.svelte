<script>
	export let name;
	export let ariaHidden = true;

	let getIcon = import(`../../icons/${name}Icon.svelte`);
</script>

{#await getIcon then { default: Icon }}
	<svelte:component this={Icon} {ariaHidden} />
{/await}
