# NavItem

The NavItem is a list item with an anchor and is meant to be used within the Navigationbar component.

## Import

```svelte
<!-- <Navigationbar /> -->
<script>
    import { NavItem } from '$lib';

    let items = [];
</script>

<nav>
	<ul>
		{#each items as item}
			<NavItem {item} />
		{/each}
	</ul>
</nav>
```
## Properties

| Name | Type   | Default   | Description |
| ---- | ------ | --------- | ----------- |
| item | Object | undefined |             |

## Accessibility

The `<NavItem />` is a `li` with an `a`. The `a` element contains an optional `<Icon />` and a `span` for the text.

## Performance

This component is build with care and coution and does not contain any unnescessary HTML elements to prevent excessive DOM tree size. The `<Icon />` components in the nav items are svg components so that the HTML contains the raw `<svg>` code.

## Dependencies

- [Icon](../../atoms/Icon/README.md)