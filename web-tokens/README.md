# Web tokens

Machine-readable brand tokens derived from the City of Mukilteo Brand Guide v1.0. Use these in any web project to stay on-brand without hand-copying hex codes from a PDF.

## Files

| File            | Use for                                                                            |
| --------------- | ---------------------------------------------------------------------------------- |
| `colors.css`    | Plain CSS custom properties — drop into any website                                |
| `colors.scss`   | SCSS variables + a `$mukilteo-colors` map for iteration/theming                    |
| `colors.json`   | Build tools, JS/TS, style-dictionary, Tailwind config, etc.                        |
| `fonts.css`     | CSS font-family stacks (brand → free fallback → system). **No font files shipped.** |
| `fonts.scss`    | SCSS equivalent                                                                    |
| `fonts.json`    | Structured font metadata (roles, brand, free fallback, license)                    |
| `fonts-google.css` | One-line drop-in that loads every free substitute from Google Fonts             |
| `FONT-SUBSTITUTES.md` | Per-font reasoning for the free substitutes + a suggested brand-guide amendment |
| `LICENSING.md`  | Why no font files are in this repo and what to do about it                         |

## CSS usage

```html
<link rel="stylesheet" href="/path/to/colors.css">
```

```css
.site-header  { background: var(--mukilteo-deep-navy); color: white; }
.button-accent { background: var(--mukilteo-aqua); }
.alert-error  { color: var(--mukilteo-red); }
```

## SCSS usage

```scss
@use "colors" as *;

.button { background: $mukilteo-deep-navy; }

// Iterate the map to generate utility classes:
@each $name, $value in $mukilteo-colors {
  .bg-#{$name} { background-color: $value; }
}
```

## JSON usage (Tailwind example)

```js
// tailwind.config.js
import mukilteo from './web-tokens/colors.json' with { type: 'json' };

export default {
  theme: {
    extend: {
      colors: {
        'mukilteo-navy': mukilteo.primary['deep-navy'].hex,
        'mukilteo-aqua': mukilteo.primary.aqua.hex,
        // ...or flatten programmatically for the full set
      },
    },
  },
};
```

## The palette

**Primary** (always-on, always-approved):

| Name       | HEX       | PMS  |
| ---------- | --------- | ---- |
| Deep Navy  | `#003660` | 2955 |
| Aqua       | `#4F9B99` | 7716 |

**Secondary** (accent use only; does not replace primary):

- **Cool:** Lavender `#929FD0` · Sky `#6FBDE9` · Blue `#659AD2` · Aqua-light `#7DC8C2` · Green-light `#B7DBA5`
- **Warm:** Wine `#952E45` · Red `#D34D4B` · Orange `#EC8D1C` · Yellow `#FEBC11`
- **Neutral:** Gray-light `#BCBEC0` · Gray `#58595B` · Black `#000000` · Brown `#635546` · Sand `#C1B8AF`

## Fonts

```css
body { font-family: var(--mukilteo-sans); }
h1   { font-family: var(--mukilteo-serif); }
.poster-headline { font-family: var(--mukilteo-display); }
```

The stacks are self-healing: if you have the brand font installed or loaded via `@font-face`, it wins. Otherwise the free open-source lookalike (from Google Fonts) is used. Otherwise a system default. **No font files ship with this repo** — see `LICENSING.md`.

### Vendor quick-start

To produce web work that matches the brand without any font licensing, add these two lines to your HTML:

```html
<link rel="stylesheet" href="/path/to/web-tokens/fonts-google.css">
<link rel="stylesheet" href="/path/to/web-tokens/fonts.css">
<link rel="stylesheet" href="/path/to/web-tokens/colors.css">
```

Then use `var(--mukilteo-sans)`, `var(--mukilteo-serif)`, `var(--mukilteo-deep-navy)`, etc. in your own CSS. See `FONT-SUBSTITUTES.md` for why each free substitute was chosen.

## Keeping in sync

The brand guide has not changed since 2015. If the guide is ever updated, all three files (`colors.css`, `colors.scss`, `colors.json`) must be updated together — the `README.md` palette table too. The HEX codes are the single source of truth; RGB/CMYK should be regenerated from HEX if edited.
