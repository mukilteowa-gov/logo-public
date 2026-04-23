# Font licensing

**Short answer: no font files are shipped with this repo.** Every font named in the City of Mukilteo Brand Guide is proprietary. You'd need a paid license from the vendor or an Adobe Creative Cloud subscription to legally use or distribute them. What this repo ships instead is CSS font-family **stacks** that try the brand font first, fall back to a free open-source lookalike, then to a system default.

## Per-font status

| Brand font                    | Vendor            | Licensing                                                                                 | Redistributable? |
| ----------------------------- | ----------------- | ----------------------------------------------------------------------------------------- | ---------------- |
| **Museo Sans** (and Condensed)| exljbris          | Commercial. The `500` weight is free to download from the foundry but web-embedding requires a separate paid license. Other weights are paid. | No |
| **Chaparral Pro**             | Adobe             | Adobe Fonts (Creative Cloud subscription). Not available outside Adobe.                   | No               |
| **Rosewood Fill**             | Adobe             | Adobe Fonts (Creative Cloud subscription).                                                | No               |
| **Avenir Next Condensed**     | Linotype/Monotype | Commercial. Paid desktop + separate paid web license.                                     | No               |
| **Georgia**                   | Microsoft         | Bundled with OS/browser — available to users, but we can't ship it.                       | No (not needed)  |
| **Arial**                     | Microsoft         | Bundled with OS/browser.                                                                  | No (not needed)  |

## The three paths forward

### 1. Do nothing — use the fallback stacks as-is

The CSS stacks in `fonts.css` will fall through to a system default on machines that don't have the brand font. The City's identity remains recognizable via the logos and colors; typography is "close enough." This is the zero-effort option and appropriate for most vendor-produced materials.

### 2. Use free open-source substitutes (recommended for web)

The stacks default to these — all served by Google Fonts under the **SIL Open Font License 1.1** (free to use, embed, and redistribute):

| Brand font                | Free substitute            | Where                                                      |
| ------------------------- | -------------------------- | ---------------------------------------------------------- |
| Museo Sans                | **Mulish**                 | https://fonts.google.com/specimen/Mulish                   |
| Museo Sans Condensed      | **Barlow Condensed**       | https://fonts.google.com/specimen/Barlow+Condensed         |
| Chaparral Pro             | **Bitter**                 | https://fonts.google.com/specimen/Bitter                   |
| Rosewood Fill             | *(no free equivalent — see note below)* | —                                                  |
| Avenir Next Condensed     | **Barlow Condensed**       | (same as above)                                            |

**Note on Rosewood Fill.** Rosewood Fill is a decorative Tuscan-style Western slab with a very specific character — thick slab serifs, flared stems, high contrast. We reviewed Google Fonts alternatives (Rye, Ewert, IM Fell English SC) and none match closely enough to substitute for display use. If you need the Rosewood Fill look, the honest options are: (a) use an Adobe Creative Cloud subscription to access it, (b) commission a custom display treatment when Rosewood's "Founded 1947" / heritage vibe is actually needed, or (c) skip the display face entirely and fall back to a heavy serif weight (Bitter at 700, for example) for feature type. Do not publish substitutes that imply equivalence when there isn't one.

To activate all of them in one shot, use the bundled `fonts-google.css` drop-in, or add the corresponding `<link>` to your HTML. The CSS stacks pick them up automatically.

**See `FONT-SUBSTITUTES.md`** for per-font visual-match reasoning and a suggested brand-guide amendment formally approving these substitutes for City web work.

### 3. License the real brand fonts

If the City wants exact brand-fidelity typography on web properties, the options are:

- **Adobe Creative Cloud subscription** — Museo Sans, Chaparral Pro, and Rosewood Fill are all available via Adobe Fonts (included with CC). Designers can use them in Illustrator/InDesign. For web, an Adobe Fonts web project embed code can be added to pages. Subscription cost is per-user.
- **Buy standalone web licenses** — MyFonts, Fonts.com, or the foundry's own site. Museo Sans web license pricing is per pageview-tier; Avenir Next Condensed is sold per-domain. These are one-time-ish purchases, but can be expensive for a municipal budget.
- **Ask your vendors** — Many print shops and agencies already have licensed copies of these fonts. They should use their own licensed copies when producing City materials; the brand guide tells them *which* fonts, not *who's paying*.

## If you ever do host licensed fonts

If the City acquires a web license, the font files still should NOT be committed to this repo — the license typically permits hosting on a specific domain, not redistribution through a public asset repo. Instead:

1. Host the `.woff2` files on the City's web server (outside this repo).
2. Add a local `@font-face` stylesheet in the project that uses them.
3. The existing CSS stacks in `fonts.css` will pick them up as the first-choice family.

There's a commented-out `@font-face` example at the bottom of `fonts.css` as a template.

## TL;DR

> You're not allowed to distribute the official fonts. The CSS in this repo handles that gracefully with fallback stacks. If a vendor wants pixel-perfect brand fidelity, they need to bring their own licensed copy.
