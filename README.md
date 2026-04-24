# City of Mukilteo — Brand & Logo Package

Official logos, brand guidelines, fonts, and color tokens for City of Mukilteo communications and web projects.

This repository is intended for City staff, vendors, and partners working on Mukilteo communications.

Use the files in this repository to keep City materials consistent.

The brand guide PDF is the authoritative source for logo use, colors, typography, and misuse rules.

Do not modify logo colors, proportions, or composition. Use only the provided files.

---

## For web developers

Three stylesheets drop in the brand palette and font stacks. The web font fallbacks are SIL OFL Google Fonts and can be used without a commercial font license. Load them from the jsDelivr CDN:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/mukilteowa-gov/logo-public@main/web-tokens/colors.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/mukilteowa-gov/logo-public@main/web-tokens/fonts.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/mukilteowa-gov/logo-public@main/web-tokens/fonts-google.css">
```

Or copy `web-tokens/` into your project and reference local paths instead.

Then in your CSS:

```css
body { font-family: var(--mukilteo-sans); color: var(--mukilteo-deep-navy); }
h1   { font-family: var(--mukilteo-sans-condensed); }
.btn { background: var(--mukilteo-aqua); color: #fff; }
```

Logos can be referenced directly:

```html
<img src="https://cdn.jsdelivr.net/gh/mukilteowa-gov/logo-public@main/primary-logo/horizontal/full-color/mukilteo-logo-horizontal-full-color.svg" alt="City of Mukilteo">
```

For a visual reference — logo use, approved backgrounds, color palette, typography, and light/dark UI examples — open `web-tokens/demo.html`.

---

## Quick start — common uses

| Need                                      | Use this                                                      |
| ----------------------------------------- | ------------------------------------------------------------- |
| Logo for a website header                 | `primary-logo/horizontal/full-color/*.svg`                    |
| Logo on a dark background                 | `primary-logo/horizontal/reversed-color/`                     |
| Logo for Word or email                    | `primary-logo/horizontal/full-color/*.png`                    |
| Small icon or social avatar               | `primary-logo/lighthouse-mark/full-color/`                    |
| Website favicon                           | `favicon/`                                                    |
| Print-ready (business card, flyer)        | `primary-logo/horizontal/full-color/*.pdf`                    |
| Editable source (`.ai` / `.psd`)          | Contact the communications office                             |
| Brand guidelines (colors, fonts, usage)   | `brand-guide/mukilteo-brand-guide.pdf`                        |
| Brand tokens for code                     | `web-tokens/colors.{css,scss,json}` · `fonts.{css,scss,json}` |

---

## Folders

| Folder                       | Contents                                                    |
| ---------------------------- | ----------------------------------------------------------- |
| `brand-guide/`               | Official brand PDF                                          |
| `primary-logo/`              | Main logo: `horizontal/`, `vertical/`, `lighthouse-mark/`   |
| `primary-logo-with-address/` | Logo paired with the mailing address                        |
| `departments/`               | Department sub-brands (Fire, Police, Recreation, etc.)      |
| `initiatives/`               | Program-specific branding (BTW, 75th Anniversary, etc.)     |
| `favicon/`                   | Browser tab icons (`.ico`, `.svg`, `.png`, `.webp`)         |
| `web-tokens/`                | CSS / SCSS / JSON brand tokens and the web brand-guide demo |
| `dist/`                      | ZIP of the whole repo for offline sharing                   |

Each `primary-logo/` orientation has four color treatments: `full-color/`, `reversed-color/` (colored lighthouse on dark backgrounds), `white/`, `black/`.

---

## File formats

| Ext     | Use for                                                   |
| ------- | --------------------------------------------------------- |
| `.svg`  | Web. Prefer this for anything digital.                    |
| `.webp` | Web, smaller than PNG when page speed matters.            |
| `.png`  | Web and docs without SVG support. Transparent background. |
| `.jpg`  | Email and Word where transparency isn't needed.           |
| `.pdf`  | Print, presentations (vector).                            |
| `.eps`  | Legacy print workflows.                                   |
| `.ico`  | Browser favicons only.                                    |

Editable source files (`.ai`, `.psd`) live with the communications office.

---

## File naming

```
mukilteo-{logo}-{orientation}-{treatment}[-{size}].{ext}
```

Examples:
- `mukilteo-logo-horizontal-full-color.svg`
- `mukilteo-logo-vertical-reversed-color.pdf`
- `mukilteo-lighthouse-mark-black.svg`
- `mukilteo-fire-horizontal.svg`

The `-{size}` suffix (e.g. `-1200w`) applies only to raster formats at a specific pixel width.

---

## Questions, or need a format not listed

Contact the City's communications office.
