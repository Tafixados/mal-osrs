# MAL OSRS Safe Refactor v1.1

This corrects the two issues found in the first safe refactor:

1. The external font/UI layer is kept at repository root, preserving its
   relative `./fonts-fixed/...` font URLs.
2. The corrected manga override is used, removing duplicate slashes and
   restoring the Combat Tasks Completed icon for Volumes.

## Upload

At repository root:
- `theme-refactor-safe-v1-1.css`
- `osrs-ui-font-layer-v4-clean.css`

In `/css/`:
- all 10 consolidated CSS files from this package

Your existing `/fonts-fixed/` folder stays exactly where it is.

## MAL

```css
@\import "https://cdn.jsdelivr.net/gh/Tafixados/mal-osrs@main/theme-refactor-safe-v1-1.css";
```

Keep v27 available until this passes your visual regression check.
