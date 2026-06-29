---
name: cgem-brand
description: "C-GEM brand skill — generates on-brand content, copy, HTML, and documents for C-GEM (Centre for Grower-centric Eco-value Mechanisms), India's only non-profit accountability partner for smallholder farming communities in carbon and ecosystem markets. Covers: marketing pages, programme communications (Carbon Ready™ / Carbon Bridge™ / Climate Learn™ / Beyond Carbon™), partnership memos, transparency dashboards, slide decks, social posts, annual reports, field updates, and the C-GEM HTML design system. Voice is grounded, rights-based, farmers as protagonists — never beneficiaries."
---

# C-GEM Brand Skill

C-GEM is India's only non-profit accountability partner for smallholder farming communities in carbon and ecosystem markets. It represents growers only — never a programme developer, buyer, or implementer. **Every artefact generated must read and look like it came from an organisation that has taken a moral position.**

> Positioning: **People-centric · Tech-enabled · Planetary-scale**
> Voice: **"Farmers First · Climate Always"**

---

## Quick-start decision tree

1. **Who reads this first?**
   - Farmer, FPO officer, CSO partner, journalist, funder → **Marketing skin** (default)
   - Carbon buyer, auditor, regulator, technical reviewer → **Platform skin** (add `.platform-skin` to root)
   - Mixed audience → Marketing skin with platform-style data tables embedded

2. **What format?** → See `templates/` for ready-to-use HTML starters.

3. **Need assets?** → Logos, brushmark, illustrations, photography all referenced in `assets/` and `references/assets.md`.

4. **Generating copy?** → Read `references/voice.md` before writing a single word.

---

## Identity — exact strings (non-negotiable)

| String | Value |
|--------|-------|
| Brand | `C-GEM` — hyphenated, ALL CAPS, always |
| Full name | `Centre for Grower-centric Eco-value Mechanisms` |
| Legal entity | `Eco-Value Empowerment Foundation` (statutory contexts only) |
| Programme 1 | `Carbon Ready™` |
| Programme 2 | `Carbon Bridge™` |
| Programme 3 | `Climate Learn™` |
| Programme 4 | `Beyond Carbon™` |

Programme names always carry the ™. Never drop it.

---

## Two skins, one core

Both skins share: pure white ground, brushmark C (real PNG asset — never a CSS text approximation), leaf green primary, Indian numerals (tabular), triplet rhythm.

```
Marketing skin (DEFAULT)          Platform skin (.platform-skin)
──────────────────────────        ──────────────────────────────
Display/Body: Geist               Space Grotesk
Voice/Accent: Newsreader Italic   JetBrains Mono (caps, no italic)
Data/Meta:    Geist Mono          JetBrains Mono
Ink:          #0E1410             #000000
Data accent:  Sprout #C8F47A      Lime #B6F569
Radii:        2/4/8/12px          0px everywhere
Feel:         Warm, human         Clinical, audit-grade
```

Apply the platform skin: `<body class="platform-skin">` or `<section class="platform-skin">`.

---

## Colour tokens (full reference in `references/tokens.md`)

**Surface**
- `--paper #FFFFFF` — the only page ground. Never cream, grey, or tonal.
- `--paper-tonal #F6F7F2` — section breaks only
- `--paper-card #F4F4EF` — cards, chips

**Ink**
- `--ink #0E1410` — primary text (warm black)
- `--ink-mute #333333` — body paragraphs
- `--ink-soft #555555` — secondary
- `--ink-faint #888888` — meta/footnote
- `--line #E8E8E6` — hairlines

**Leaf (brand green)**
- `--leaf-600 #2C7A3D` — **PRIMARY brand green**
- `--leaf-800 #1F5A2C` — hover/press
- `--leaf-700 #265E30` — voice text colour
- `--leaf-100 #D8ECDC` / `--leaf-050 #ECF5EE` — tints

**Accents — sparing, semantic, not decorative**
- `--sprout #C8F47A` — marketing data highlight
- `--lime #B6F569` — platform live data
- `--clay-600 #B85829` — Beyond Carbon™ accent
- `--harvest #C98A1F` — Carbon Ready™ accent
- `--signal #FF7A3A` — alerts, use rare
- `--sky #3A5FA8` — **EEF statutory stamp ONLY. Never reuse.**

**Programme accent map** (in code: `[data-programme="ready|bridge|learn|beyond"]`)
- Carbon Ready™ → `--harvest`
- Carbon Bridge™ → `--ink`
- Climate Learn™ → `--leaf-600`
- Beyond Carbon™ → `--clay-600`

---

## Typography (full reference in `references/typography.md`)

**Scale:** display `clamp(48px,6.5vw,96px)` · h1 `clamp(36px,4.5vw,64px)` · h2 `clamp(30px,3.6vw,48px)` · h3 24px · h4 20px · lede 18px · body 16px · small 14px · micro 12px · mono 11px

Headings: weight 500, line-height 1.05, tracking −0.025em to −0.035em. Body: line-height 1.5–1.65.

**Numerals:** Indian grouping always (`2,71,000` never `271,000`). `font-variant-numeric: tabular-nums` on every stat or data column.

**Devanagari moments:** `font-family: var(--font-devanagari)` for Hindi, weight 600. Pair with Newsreader Italic emphasis.

---

## Type roles — use these CSS classes

All tokens and the classes below live in `colors_and_type.css` at the skill root. Every template links it (`<link rel="stylesheet" href="../colors_and_type.css">`); link it the same way in new HTML rather than re-declaring tokens.

```
.voice       Newsreader italic, leaf-700. Community quotes, ledes, emphasis.
             Platform: mono caps instead.
.triplet     Signature rhythm. Mono caps, green dots. "Farmers First · Climate Always"
.stat        Big tabular-num figure. Include <span class="unit"> child.
             .unit must use `font-size: clamp(11px, 0.32em, 18px)` — never bare `0.32em`.
.eyebrow     Mono 11px caps, 0.12em tracking, leaf-600. Section labels ONLY.
.hl          Sprout/lime inline highlight on emphasis word.
.lede        18px intro paragraph, max-width 60ch.
.footnote    10.5px mono caps, ink-faint.
.attribution Same as footnote.
.mono        Code chip on --paper-card.
.deva        Devanagari helper, weight 600.
.brushmark-bg  Brushmark backdrop on a section — use `assets/logos/logo-brushmark.png` as `background-image`, never a CSS text "C" or SVG path approximation. Opacity by role: 6–10% as a hero/section watermark (`.brushmark-bg` helper defaults to 7%); up to 12–14% as a centred voice anchor on a paper-tonal cover section. From a file in `templates/` the relative path is `../assets/logos/logo-brushmark.png`; embed as base64 if the file will be opened standalone.
```

**Geist Mono discipline — critical:** Geist Mono is a precision instrument, not wallpaper. Overusing it (eyebrows on every section, all stat units, all footnotes, all chips, the triplet, the CTA label) makes the output read as generic AI-generated design. Use it for: `.eyebrow` section labels, `.stat` figures, `.triplet` signature lines, `.footnote`/`.attribution` meta. Do NOT use it for: body copy, sub-headings, button labels, card descriptions, or any text a reader actually reads for meaning. If in doubt, use Geist (the display/body font) instead. The contrast between Newsreader Italic (warm, human) and Geist Mono (precise, functional) is what makes the brand feel intelligent — not the mono font itself.

**Buttons:** `.btn--primary` (ink bg → leaf-800 hover) · `.btn--secondary` (outlined) · `.btn--leaf` · `.btn--ghost`

**Components:** `.chip` · `.chip--leaf` · `.card` · `.card--ink` · `.index-list`

---

## Logo rules

Assets in `assets/logos/` — horizontal, stacked, logomark variants in black/white/inverse/full-colour.

- **Clear space:** half the cap-height of "C-GEM" on all sides minimum
- **Never** recolour the brushmark arc
- **Never** substitute the brushmark with a CSS text character, SVG arc, or ::before pseudo-element — always use `assets/logos/logo-brushmark.png`
- **Never** place Full Colour on coloured, patterned, or photographic backgrounds — use White or Inverse there
- **Never** crop, stretch, skew, or rotate
- **Minimum:** 80px wide (digital), 18mm (print)
- Brushmark C, three sanctioned modes: hero/section watermark (6–10% opacity), centred voice anchor (up to 12–14% on paper-tonal), inline cap-height nav mark — always green, never recoloured or cropped

---

## Photography & illustration

Photography in `assets/photography/`, illustrations in `assets/illustrations/`.

- Documentary, warm-graded, agricultural. Farmers as protagonists — not scenery.
- Natural light, warm-neutral tones. No heavy filters, no blue grading.
- Text on photos: dark scrim ≤55% opacity. Never a solid colour block.
- When no photo available: `repeating-linear-gradient` placeholder with mono caption.
- Never: posed portraits, abstract nature shots, AI-generated landscapes, corporate stock.

---

## Hard facts — use these, formatted exactly

Since 2022:
- **2,71,000 farming families**
- **5 verified projects**
- **14 Indian states**

Key partners: AKRSP (India), Varaha Climate Ag., Fair Climate Fund India, Gram Vikas, Cohesion Foundation Trust, Shroffs Foundation Trust, FES, LANDSTACK, LGT Venture Philanthropy, Jain Irrigation, Godavari Biorefineries, Rainmatter Foundation.

---

## Pre-delivery checklist

Before finishing any artefact, verify every item:

1. Skin chosen by first reader? White ground only?
2. All numerals Indian-format? Tabular figures where numeric?
3. "Beneficiary/beneficiaries" absent? Hype words absent? Emoji absent?
4. Programme names carry ™? Brand strings exact?
5. Colours from token list — accents semantic, not decorative?
6. Voice moments in Newsreader Italic (or mono caps in platform skin)?
7. Logo on clean ground with clear space, ≥80px?
8. Sky `#3A5FA8` only on EEF statutory stamp — nowhere else?
9. Brushmark is `assets/logos/logo-brushmark.png` (not a CSS text char or SVG arc) at a sanctioned opacity — 6–10% watermark, up to 12–14% only as a centred voice anchor?
10. Geist Mono used sparingly (labels, stats, meta only) — not on body copy or button text?
11. Copy contains no "no stake in credits" or similar language about C-GEM's financial position in the market?

---

## Reference files

Read these when you need more depth:

- `references/voice.md` — full voice & tone guide, banned words, canonical phrases, casing rules
- `references/tokens.md` — complete CSS token reference with usage notes
- `references/typography.md` — type scale, font loading, Devanagari, numerals
- `references/assets.md` — asset inventory with file paths and usage rules
- `references/programmes.md` — four programme descriptions, accents, copy angles

## Templates

Start here for common artefact types:

- `templates/marketing-page.html` — full marketing surface (hero, stats, programme tiles, CTA)
- `templates/platform-dashboard.html` — transparency/methodology surface
- `templates/email-memo.html` — partnership memo / funder update
- `templates/slide-deck.html` — presentation template (both skins)
