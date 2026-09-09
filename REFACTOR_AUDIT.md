# MAL-OSRS Safe Refactor v1.1

## Corrections

### Fonts
The font layer is restored to the repository root as:

`/osrs-ui-font-layer-v4-clean.css`

This is necessary because its `@font-face` rules use relative URLs such as:

`./fonts-fixed/RUNESCAPE-CHAT-07.woff2`

Moving the layer into `/css/` changes the URL base to `/css/fonts-fixed/`,
which does not exist.

### Manga
The stale manga source used in safe-v1 has been replaced by the corrected
working version.

That correction:
- removes the extra CSS-generated `" / "` before chapter/volume totals
- restores the manga Volumes icon using the OSRS Combat Tasks Completed icon

## Structure
- 1 root font/UI layer
- 10 consolidated `/css/` modules
- 1 master theme

## Consolidated declaration payload SHA-256
`f5595b3b284d646d7f55aa0a4979d6efb1c7adcf83236f6a75a35f2ae316b2f1`

## Regression checks
Test:
- fonts
- anime compact cards
- manga chapter / volume counts
- manga Volumes icon
- search
- score dropdown
- sidebar
- filters
- footer
- minimap
- optional fields
