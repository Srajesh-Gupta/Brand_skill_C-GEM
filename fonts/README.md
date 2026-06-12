# Font Files

C-GEM v2.0 uses **self-hosted variable WOFF2 files** — no network dependency, no Google Fonts. All six files live in this folder and are registered via `@font-face` at the top of `/colors_and_type.css`.

## Files

| File | Family | Style | Weight range |
|---|---|---|---|
| `geist-normal-100_900__1_.woff2` | **Geist** | normal | 100–900 |
| `geist-mono-normal-100_900.woff2` | **Geist Mono** | normal | 100–900 |
| `newsreader-italic-200_800.woff2` | **Newsreader** | italic only | 200–800 |
| `space-grotesk-normal-300_700.woff2` | **Space Grotesk** | normal | 300–700 |
| `jetbrains-mono-normal-100_800.woff2` | **JetBrains Mono** | normal | 100–800 |
| `noto-sans-devanagari-normal-100_900.woff2` | **Noto Sans Devanagari** | normal | 100–900 |

All files are variable fonts — a single file covers the full declared weight range. No separate per-weight files needed.

## Marketing skin (default)

| Use | Font | Weights used |
|---|---|---|
| **Display + Body** | Geist | 300 · 400 · 500 · 600 · 700 |
| **Voice (italic only)** | Newsreader | Italic 400 · 500 |
| **Data + Meta** | Geist Mono | 400 · 500 · 600 |

## Platform skin (`.platform-skin`)

| Use | Font | Weights used |
|---|---|---|
| **Display + Body** | Space Grotesk | 300 · 400 · 500 · 600 · 700 |
| **Voice + Data + Meta** | JetBrains Mono | 400 · 500 · 600 |

## Multilingual

| Use | Font |
|---|---|
| **Hindi / Devanagari** | Noto Sans Devanagari |

---

## Type role classes

Use the classes below from `colors_and_type.css` rather than ad-hoc styling. They are skin-aware — the same class produces the right family for whichever skin is active.

| Role | Class | Marketing | Platform |
|---|---|---|---|
| **Headline** | `h1`–`h4`, `.display` | Geist 500 · −0.04em | Space Grotesk 500 |
| **Voice** | `.voice`, `<em>` | Newsreader Italic | JetBrains Mono uppercase |
| **Body** | default `<p>`, `.lede` | Geist 400 | Space Grotesk 400 |
| **Data / stat** | `.stat`, `.stat .unit` | Geist 500 + Newsreader unit | Space Grotesk + Mono unit |
| **Eyebrow** | `.eyebrow` | Geist Mono leaf-600 | JetBrains Mono leaf-600 |
| **Footnote / meta** | `.footnote`, `.attribution` | Geist Mono 10.5px | JetBrains Mono 10.5px |
| **Triplet** | `.triplet > span` | Geist Mono caps · forest dots | JetBrains Mono caps · forest dots |
| **Inline highlight** | `.hl` | Sprout (#C8F47A) | Lime (#B6F569) |
| **Multilingual** | `.deva` | Noto Sans Devanagari | Noto Sans Devanagari |

## Numerals

Always:
- Indian numbering format: `2,71,000` not `271,000`
- Tabular figures: `font-variant-numeric: tabular-nums` (set on `.stat` automatically)
- Unit treatment: italic Newsreader in marketing, uppercase JetBrains Mono in platform
