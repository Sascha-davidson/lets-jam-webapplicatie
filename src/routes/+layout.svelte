<script>
	import NavigationBar from '$lib/organisms/NavigationBar.svelte';
</script>

<header>
	<NavigationBar />
</header>

<slot />

<style>
	header {
		height: 100%;
	}
</style>
