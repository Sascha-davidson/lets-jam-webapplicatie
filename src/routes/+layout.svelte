<script>
	import { Navigationbar } from '$lib';
</script>

<header>
	<Navigationbar />
</header>

<slot />

<style>
	@import '$lib/styles/global.css';

	header {
		height: 100%;
	}
</style>
