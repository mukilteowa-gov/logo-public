# Free font substitutes

For each font named in the City of Mukilteo brand guide, this doc recommends a **free, open-source substitute** available on Google Fonts under the SIL Open Font License 1.1 — meaning anyone can use, embed, or redistribute them without paying for a license.

These substitutes are what the CSS stacks in `fonts.css` fall back to when the official brand font isn't available.

## The five pairings

### 1. Museo Sans → [Mulish](https://fonts.google.com/specimen/Mulish)

**Why:** Museo Sans is a humanist/geometric sans with slightly quirky, friendly letterforms. Mulish (formerly Muli) has a very similar character — warm geometric shapes, good x-height, readable at small sizes. It ships with a huge weight range (200–1000), which matters for design flexibility.

**Weights to load:** `300`, `400`, `500`, `700`, `900` (matches Museo Sans's published weight set).

**Runner-up:** Lato — more conservative, very widely recognized. Use if your audience skews older and brand familiarity matters more than exact visual match.

---

### 2. Museo Sans Condensed → [Barlow Condensed](https://fonts.google.com/specimen/Barlow+Condensed)

**Why:** Barlow Condensed is a well-balanced condensed sans that works at both small label sizes and large headline sizes. It's one of the most widely-adopted condensed fonts on the web.

**Weights to load:** `400`, `500`, `600`, `700`.

**Runner-up:** Fira Sans Condensed — warmer, more humanist; a touch closer to Museo Sans's character but less recognized.

---

### 3. Chaparral Pro → [Bitter](https://fonts.google.com/specimen/Bitter)

**Why:** Chaparral Pro is a "semi-slab" serif — it reads as a traditional serif but has subtle slab-serif qualities. Bitter was designed specifically for on-screen body text, and has the same semi-slab warmth. Renders beautifully at body sizes on low-DPI screens.

**Weights to load:** `400`, `500`, `700`.

**Runner-up:** Source Serif 4 — a purer transitional serif; less slab character but excellent readability. Zilla Slab is another solid alternative if you want more pronounced slab features.

---

### 4. Rosewood Fill → *(no free substitute — see explanation)*

**Why no pick:** Rosewood Fill is a decorative Tuscan-style Western slab. We reviewed three OFL candidates (Rye, Ewert, IM Fell English SC) side-by-side with the real Rosewood Fill specimen and none of them match closely enough to honestly substitute. Rye is the closest match by category (vintage Western slab) but is noticeably lighter in weight and lacks the decorative Tuscan features. Ewert is heavier but reads as "Wild West saloon sign," which drifts from the Pacific Northwest ferry-town identity. IM Fell English SC reinterprets the role as 17th-century English, which is a different lane entirely.

**What to do instead.** Rosewood Fill is only used in the City's logotype (the word "MUKILTEO"), where it's already baked into the vector files as outlined text — vendors never need to retypeset it. For the rare case where a display face is needed for feature type (event posters, "Founded 1947" signage), the options are:

1. **Use Adobe Creative Cloud.** Rosewood Fill is available in Adobe Fonts with a CC subscription. City designers and most print-shop vendors already have CC.
2. **Fall back to a heavy serif weight** — Bitter at weight 700 has enough presence to carry a feature headline without pretending to be something it isn't.
3. **Commission custom display type** for campaigns where Rosewood's specific heritage character really matters.

The CSS stack in `fonts.css` for the `display` role keeps Rosewood Fill as first choice and falls back to heavy serif / system display fonts — it no longer names an OFL substitute, since we don't have one that's honest.

---

### 5. Avenir Next Condensed → [Barlow Condensed](https://fonts.google.com/specimen/Barlow+Condensed)

**Why:** The brand guide uses Avenir Next Condensed Demi Bold specifically for the "CITY OF" text that sits above "MUKILTEO" in the logo. That text is already baked into the vector logo files, so **you never need to retypeset it.** The only reason to match this font is for caption text immediately adjacent to the logo — e.g. "City Council" below "CITY OF MUKILTEO" in a sub-brand signature.

For that use, Barlow Condensed (which you're already loading for the condensed sans role) does fine double-duty. No additional font needed.

**Runner-up:** Saira Condensed — more geometric, closer to Avenir's character; load only if you're picky about this one caption.

---

## What this means for the brand guide

If the City adopts this pairing list officially — i.e. amends the brand guide to say "where the original fonts aren't available or licensed, use these substitutes" — that solves the font problem for:

- Vendors producing web work (forms portals, the city website, online documents)
- Staff using Google Docs, Microsoft 365 with Google Fonts add-ins, Canva, etc.
- Print shops that don't already have Adobe Creative Cloud

**Suggested brand guide amendment text:**

> **Web and free-substitute typography.** For digital applications where the preferred brand fonts are not available, the following Google Fonts substitutes are approved: Mulish (for Museo Sans), Barlow Condensed (for Museo Sans Condensed and Avenir Next Condensed), and Bitter (for Chaparral Pro). All three are licensed under the SIL Open Font License 1.1 and may be freely embedded in websites and digital products.
>
> Rosewood Fill has no approved free substitute. It is used only in the logotype, which is already distributed as outlined vector art; vendors do not need to retypeset it. For the rare case where Rosewood Fill is needed outside the logotype, designers should use a licensed copy via Adobe Creative Cloud or substitute a heavy serif weight of Bitter.

The CSS in `fonts.css` already implements this preference order — brand font first, substitute second, system fallback last — so no code changes are needed when the guide is updated.

---

## Loading the substitutes

The simplest path:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Mulish:wght@300;400;500;700;900&family=Barlow+Condensed:wght@400;500;600;700&family=Bitter:wght@400;500;700&display=swap">

<link rel="stylesheet" href="/path/to/web-tokens/colors.css">
<link rel="stylesheet" href="/path/to/web-tokens/fonts.css">
```

Or, equivalently, use the bundled `fonts-google.css` which contains the same `@import` — one fewer `<link>` tag.

## License summary for the substitutes

All three substitute fonts (Mulish, Barlow Condensed, Bitter) are licensed under the **SIL Open Font License 1.1**. This allows:

- ✓ Free use for any purpose — personal, commercial, public-sector
- ✓ Self-hosting the font files on the City's own server
- ✓ Embedding in websites, apps, and digital documents
- ✓ Modifying (within OFL terms)
- ✓ Redistributing — including as part of this repo if the City ever decides to bundle the `.woff2` files directly

The only restriction is that the original font names can't be used for a modified version (name change required if modifying), and OFL fonts can't be sold standalone. None of that affects normal use.
