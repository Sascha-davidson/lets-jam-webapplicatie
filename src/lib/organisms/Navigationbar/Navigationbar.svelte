<script>
	import { NavItem } from '$lib';

	let items = [
		{ icon: 'Home', label: 'Home', href: '/' },
		{ icon: 'Players', label: 'Players', href: '/players' },
		{ icon: 'Teams', label: 'Teams', href: '/teams' },
		{ icon: 'Tournaments', label: 'Tournaments', href: '/tournaments' }
		// { icon: 'Live', label: 'Live', href: '/live' }
	];
</script>

<nav aria-label="Main Navigation">
	<ul>
		{#each items as item}
			<NavItem {item} />
		{/each}
	</ul>
</nav>

<style>
	nav {
		padding: 1em;
		height: 100%;
	}

	ul {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		gap: 2rem;
		box-shadow: var(--box-shadow);
		border-radius: 10px;
		background-color: var(--input-background-color);
		height: 100%;
		list-style: none;
	}

	@media only screen and (max-width: 500px) {
		nav {
			display: none;
		}
	}
</style>
