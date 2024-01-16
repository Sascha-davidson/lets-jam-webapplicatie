<script>
	export let name;

	let Icon = import(`../../icons/${name}Icon.svelte`).default;
</script>

<svelte:component this={Icon} />
