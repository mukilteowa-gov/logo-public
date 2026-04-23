# City of Mukilteo — Brand & Logo Package

Official logos, marks, and brand guidelines for the City of Mukilteo. This package is intended for web designers, vendors, print shops, partners, and anyone producing materials on behalf of the City.

---

## Building a website or web app? Start here.

For vendors producing web work (portals, forms, microsites), three stylesheets get you on-brand with zero font-licensing concerns:

```html
<link rel="stylesheet" href="/path/to/web-tokens/fonts-google.css">
<link rel="stylesheet" href="/path/to/web-tokens/fonts.css">
<link rel="stylesheet" href="/path/to/web-tokens/colors.css">
```

Then in your CSS:

```css
body { font-family: var(--mukilteo-sans); color: var(--mukilteo-deep-navy); }
h1   { font-family: var(--mukilteo-serif); }
.button-primary { background: var(--mukilteo-aqua); }
```

Grab the logo from `primary-logo/horizontal/full-color/mukilteo-logo-horizontal-full-color.svg`. Favicon from `favicon/`.

That's the whole brand system in a web context. Everything in this repo is free to use and redistribute, and the fonts are Google Fonts (SIL OFL licensed). See `web-tokens/` for details.

---

## Quick start

**Most people want one of these:**

| Need                                  | Grab this                                                             |
| ------------------------------------- | --------------------------------------------------------------------- |
| A logo for a website header           | `primary-logo/horizontal/full-color/mukilteo-logo-horizontal.svg`     |
| A logo on a dark background           | `primary-logo/horizontal/reversed-color/`                             |
| A logo for a Word doc or email        | `primary-logo/horizontal/full-color/mukilteo-logo-horizontal.png`     |
| Small icon / social avatar            | `primary-logo/lighthouse-mark/full-color/`                            |
| Website favicon                       | `favicon/favicon.ico`                                                 |
| Print material (business card, flyer) | `primary-logo/horizontal/full-color/mukilteo-logo-horizontal.pdf`     |
| Editable source (designer)            | Contact the City's communications office for `.ai` / `.psd` originals |
| Brand colors, typography, usage rules | `brand-guide/mukilteo-brand-guide.pdf`                                |
| Brand colors for a website (CSS/SCSS/JSON) | `web-tokens/colors.css` · `colors.scss` · `colors.json`          |

---

## What's in each folder

- **`brand-guide/`** — Official brand guidelines (colors, typography, clear-space rules).
- **`primary-logo/`** — The main City of Mukilteo logo, in three orientations:
  - `horizontal/` — Long form, best for headers and wide spaces.
  - `vertical/` — Stacked form, best for square spaces.
  - `lighthouse-mark/` — The lighthouse icon alone (for avatars, favicons, small uses).
  - Each orientation has four color treatments:
    - `full-color/` — Default, use on white/light backgrounds.
    - `reversed-color/` — Colored lighthouse with white text, use on dark/photo backgrounds.
    - `white/` — All white, use on dark/photo backgrounds when single-color is required.
    - `black/` — All black, use for single-color print or faxes.
- **`primary-logo-with-address/`** — City logo paired with the mailing address (letterhead, formal docs).
- **`departments/`** — Sub-brand logos for City departments (Fire, Police, Recreation, etc.).
- **`initiatives/`** — Time-limited or program-specific branding (BTW, 75th Anniversary, etc.).
- **`favicon/`** — Browser tab icons (`.ico` + sized PNG favicons).
- **`web-tokens/`** — Brand colors as CSS custom properties, SCSS variables, and JSON. Pulls the official palette out of the brand-guide PDF so web projects can use it directly.
- **`dist/`** — Packaged ZIP of this whole repo, for sharing as a single file.

---

## File formats available

For each logo, the following formats are provided wherever possible:

| Format | Use for                                                          |
| ------ | ---------------------------------------------------------------- |
| `.svg` | Web, any size, tiny file. **Prefer this for anything digital.**  |
| `.png` | Web/docs where SVG isn't supported. Transparent background.      |
| `.webp`| Modern web, smaller than PNG. Use when page speed matters.       |
| `.jpg` | Email, Word docs, anywhere transparency isn't needed.            |
| `.pdf` | Print, presentations (vector, scales infinitely).                |
| `.eps` | Legacy print workflows, professional print shops.                |
| `.ico` | Browser favicons only.                                           |

Editable source files (`.ai`, `.psd`) are maintained internally by the City's communications office. Contact them if you need one.

---

## File naming convention

Files follow this pattern:

```
mukilteo-{logo}-{orientation}-{treatment}[-{size}].{ext}
```

Examples:
- `mukilteo-logo-horizontal-full-color.svg`
- `mukilteo-logo-horizontal-full-color-1200w.png`
- `mukilteo-logo-vertical-reversed-color.pdf`
- `mukilteo-lighthouse-mark-black.svg`
- `mukilteo-fire-horizontal.svg`

The `-{size}` suffix (e.g. `-1200w`) is only used for raster formats with a specific pixel width.

---

## Questions / need a format not listed?

Contact the City's communications office.
