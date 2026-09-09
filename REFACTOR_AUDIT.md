# MAL-OSRS Safe Refactor v1 Audit

## What this pass does

This is the conservative first stage of the refactor.

Instead of trying to semantically rearrange the historical CSS immediately,
the v27 source files are grouped into 10 **contiguous** modules. That matters
because CSS cascade order is part of the behavior.

The original source declarations are not edited or reordered in this pass.

## Verification

- Active v27 source files represented: **29**
- New imports: **10**
- Declaration payload SHA-256 before grouping:
  `6e2e3d48f08a9afe60e1a0103f720e3973eae28a487312010748db1976844117`
- Declaration payload SHA-256 after grouping:
  `6e2e3d48f08a9afe60e1a0103f720e3973eae28a487312010748db1976844117`
- Payloads match exactly: **YES**

The only v27 import intentionally omitted is:

`28-minimap-full-route-v1.css`

It defines only the old 2048px-scaled version of:
- `--rs-minimap-route-scroll-distance`
- `@keyframes rs-minimap-route`

and is immediately superseded by `29-minimap-full-route-native-v1.css` in the
working theme.

## Why this is safer than an aggressive cleanup

The old project contains many selectors that overlap through specificity and
later overrides. Moving rules into prettier semantic files can change the
cascade even when the declarations themselves look equivalent.

This pass first establishes a smaller project structure while preserving the
v27 ordering exactly. Once you confirm visual parity in MAL, Refactor v2 can
collapse duplicated historical card/search/sidebar rules subsystem by
subsystem.

## New module map

### `00-foundation-fonts.css`
- `osrs-ui-font-layer-v4-clean.css`
- `00-foundation.css`

### `01-shell-banner-nav.css`
- `01-banner-v2.css`
- `02-tabs.css`
- `03-list-shell.css`

### `02-cards-sidebar-dialogs-base.css`
- `04-cards-base.css`
- `05-sidebar-base.css`
- `06-dialogs-footer-responsive.css`

### `03-cards-polish-icons.css`
- `07-cards-layout-v42.css`
- `08-card-details-v43.css`
- `09-ui-polish-v44.css`
- `10-card-polish-v45.css`
- `11-card-final-v46.css`
- `12-infobox-icons.css`

### `04-sidebar-tooltips-visitor.css`
- `13-sidebar-final-v2.css`
- `14-tooltips-v2.css`
- `15-visitor-strip-v5.css`

### `05-manga-optional-fields.css`
- `16-manga-overrides-v1.css`
- `22-optional-fields-v6.css`

### `06-footer-stats-progress.css`
- `24-footer-progress-score-v2.css`
- `26-stats-minimap-v3.css`
- `27-anime-plus-fix-v1.css`

### `07-minimap-footer.css`
- `29-minimap-full-route-native-v1.css`
- `30-footer-legal-cursor-v1.css`
- `31-footer-readable-legal-v1.css`

### `08-search-filter-score.css`
- `32-search-style-filter-v1.css`
- `34-search-score-polish-v1.css`

### `09-search-final.css`
- `35-search-below-nav-score-compact-v1.css`
- `36-search-banner-corner-v1.css`

## Regression checklist

Compare against `theme-v27.css`:

1. Anime list
2. Manga list
3. Own-list view
4. Visitor / logged-out view
5. Every status tab
6. Search closed/open in banner corner
7. Sidebar capstones and hover tooltips
8. Card notch geometry
9. Anime progress + icon
10. Manga chapters / volumes + icons
11. Score selector
12. Optional columns with everything enabled
13. Stats ribbon
14. Filters dialog
15. Footer prompt / cursor / legal text
16. Minimap visibility at wide/narrow widths and browser zoom
17. Full minimap scroll path
18. Long-list lazy loading

If those match v27, the next step is the real code reduction pass.
