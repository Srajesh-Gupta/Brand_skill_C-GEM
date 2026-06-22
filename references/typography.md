# C-GEM Typography Reference

## Font families

### Marketing skin (default)

| Role | Family | Weights | Notes |
|------|--------|---------|-------|
| Display + Body | Geist | 100–900 | Modern grotesque. 500 for headings. |
| Voice / Accent | Newsreader | 200–800 italic | Italic ONLY. No roman cut. |
| Data + Meta | Geist Mono | 100–900 | Eyebrows, captions, code labels. |
| Hindi | Noto Sans Devanagari | 100–900 | Weight 600 at display size. |

### Platform skin (`.platform-skin`)

| Role | Family | Weights | Notes |
|------|--------|---------|-------|
| Display + Body | Space Grotesk | 300–700 | Slightly more characterful, reads as platform. |
| Voice / Data | JetBrains Mono | 100–800 | Caps + 0.06em tracking when used as voice. |
| Meta | JetBrains Mono | — | Eyebrows use `[01]` bracketed indices. |

### CSS variable aliases

```css
--font-geist:           'Geist', system-ui, -apple-system, 'Segoe UI', sans-serif
--font-newsreader:      'Newsreader', Georgia, 'Times New Roman', serif
--font-geist-mono:      'Geist Mono', ui-monospace, 'SF Mono', Menlo, monospace
--font-space-grotesk:   'Space Grotesk', system-ui, sans-serif
--font-jetbrains-mono:  'JetBrains Mono', ui-monospace, 'SF Mono', Menlo, monospace
--font-devanagari:      'Noto Sans Devanagari', sans-serif

/* Skin-aware aliases (use these) */
--font-display  /* Geist or Space Grotesk */
--font-body     /* Geist or Space Grotesk */
--font-voice    /* Newsreader italic or JetBrains Mono */
--font-data     /* Geist Mono or JetBrains Mono */
--font-meta     /* Geist Mono or JetBrains Mono */
```

### Self-hosted font files (in `assets/fonts/`)

```
geist-normal-100_900__1_.woff2
geist-mono-normal-100_900.woff2
newsreader-italic-200_800.woff2
space-grotesk-normal-300_700.woff2
jetbrains-mono-normal-100_800.woff2
noto-sans-devanagari-normal-100_900.woff2
```

Google Fonts CDN fallback (for online environments):
```html
<link href="https://fonts.googleapis.com/css2?family=Geist+Mono:wght@100..900&family=Geist:wght@100..900&family=JetBrains+Mono:ital,wght@0,100..800;1,100..800&family=Newsreader:ital,opsz,wght@1,6..72,200..800&family=Noto+Sans+Devanagari:wght@100..900&family=Space+Grotesk:wght@300..700&display=swap" rel="stylesheet">
```

---

## Type scale

| Token | Value | Role |
|-------|-------|------|
| `--fs-mega` | `clamp(56px, 9vw, 144px)` | Cover only |
| `--fs-display` | `clamp(48px, 6.5vw, 96px)` | Hero |
| `--fs-h1` | `clamp(36px, 4.5vw, 64px)` | Page title |
| `--fs-h2` | `clamp(30px, 3.6vw, 48px)` | Section head |
| `--fs-h3` | `24px` | Subsection |
| `--fs-h4` | `20px` | Label-level head |
| `--fs-lede` | `18px` | Intro paragraph |
| `--fs-body` | `16px` | Default body |
| `--fs-small` | `14px` | Secondary body |
| `--fs-micro` | `12px` | Captions |
| `--fs-mono` | `11px` | Eyebrows, footnotes |

## Tracking (letter-spacing)

```css
--tracking-tight:    -0.04em    /* large display */
--tracking-display:  -0.035em   /* hero headings */
--tracking-h1:       -0.025em   /* h1 */
--tracking-h2:       -0.02em    /* h2 */
--tracking-normal:    0
--tracking-mono:      0.06em    /* mono in platform voice mode */
--tracking-eyebrow:   0.12em    /* all caps labels */
```

## Line heights

```css
--lh-tight:   0.93   /* mega/display */
--lh-snug:    1.05   /* headings */
--lh-normal:  1.5    /* body default */
--lh-loose:   1.65   /* long-form body */
```

---

## Numerals — hard rules

1. **Indian grouping system always:** `2,71,000` — never `271,000`. The comma falls after 2 digits from the right for thousands, then every 2 digits.
2. **Lakh/crore for domestic contexts:** "27 lakh farming families" not "2.7 million" when writing for Indian audiences.
3. **Tabular figures on all data:** `font-variant-numeric: tabular-nums` on every stat column, data table, or metric display.
4. **Units:** Italic-serif unit in marketing skin (`.unit` child inside `.stat`). Mono uppercase unit in platform skin. Always `font-size: clamp(11px, 0.32em, 18px)` — bare `0.32em` computes to ~7px at mobile stat sizes.

Examples:
```
2,71,000 farming families   ✓
271,000 farming families    ✗
27.1 lakh                  ✓ (domestic)
2.71 million               ✗ (sounds corporate)
```

---

## Devanagari moments

For any Hindi headline or community-facing copy in Hindi:
```html
<span class="deva">किसानों की आवाज़</span>
```

`.deva` applies `font-family: var(--font-devanagari); font-weight: 600`.

Pairing: Devanagari headline → Newsreader Italic translation/emphasis below it.

Never set Devanagari in a Latin-only font — it falls back to tofu (blank squares).

---

## HTML baseline setup

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <link rel="stylesheet" href="../colors_and_type.css">  <!-- from templates/ -->
  <!-- Optional: Lucide icons -->
  <script src="https://unpkg.com/lucide@latest"></script>
</head>
<body>
  <!-- Marketing skin: nothing extra -->
  <!-- Platform skin: <body class="platform-skin"> -->
</body>
</html>
```

Body baseline (already in `colors_and_type.css`): Geist, 16px, 1.5 line-height, `--ink` colour, `optimizeLegibility`, antialiased.
