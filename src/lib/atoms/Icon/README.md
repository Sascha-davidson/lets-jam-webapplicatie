# NavItem

The `<Icon />` component is some sort of wrapper for the `svg` icons. The component dynamically loads the icon with the name you provide.

## Import

### Basic

```svelte
<script>
    import { Icon } from '$lib';
</script>

<Icon name={'Home'} />
```

### With alt text

```svelte
<script>
    import { Icon } from '$lib';
</script>

<Icon name={'Home'} ariaHidden={false} />
```

## Accessibility

The `<Icon />` is a `<svg>`. Icons are most times purely visual and do not require an `alt` text, however every icons should contain an `alt` text, but the `svg`'s have by default an `aria-hidden="true"` property applied. If you want to set `aria-hidden` to `false` you can add `ariaHidden={false}` to the `<Icon />` tag.

## Performance

This component loads the icon on the client. The component loads in the `svg` for the best performance.

## Dependencies

None.