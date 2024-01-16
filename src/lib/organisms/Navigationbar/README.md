# Navigationbar

The Navigationbar is a vertical navigation component.

## Import

```svelte
<script>
    import { Navigationbar } from '$lib';
</script>

<Navigationbar />
```

## Properties

None.

## Accessibility

The `<Navigationbar />` component is created with the `nav` HTML element which describes that the element contains navigation. The `nav` contains an `ul` which indicates that there is a list with navigation links. The `<Navigationbar />` component imports the `<NavItem />` component. The `<NavItem />` is a `li` with an `a`. The `a` element contains an optional `<Icon />` and a `span` for the text.

### Keyboard support

| Key | Function |
| --- | -------- |
| tab | Add focus to the first item if focus moves in to the menu. If the focus is already within the menu, focus moves to the next focusable item in the page tab sequence. |

## Performance

This component is build with care and coution and does not contain any unnescessary HTML elements to prevent excessive DOM tree size. The icons in the nav items are svg components so that the HTML contains the raw `<svg>` code.

## Dependencies

- [NavItem](../../molecules/NavItem/README.md)