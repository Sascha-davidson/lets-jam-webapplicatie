<script>
	import { Icon } from '$lib';

	export let item;
</script>

<li>
	<a href={item.href}>
		<Icon name={item.icon} />
		<span>{item.label}</span>
	</a>
</li>

<style>
	li {
		width: 100%;
	}

	a {
		display: flex;
		flex-flow: column nowrap;
		justify-content: center;
		align-items: center;
		gap: 0.5em;
		transition: 0.2s;
		padding: 1em;
		aspect-ratio: 1;
		width: 100%;
		color: var(--primary-font-color);
		font-family: var(--secondary-font-family);
		text-decoration: none;
	}

	a:is(:hover, :focus) {
		background: rgba(0, 0, 0, 0.1);
	}
</style>
