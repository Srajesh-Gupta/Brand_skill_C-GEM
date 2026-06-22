# Design System: C-GEM — Centre for Grower-centric Eco-value Mechanisms

> Field notebook, not landing page — warm near-black ink on pure white, one confident leaf green, hairline rules and triplet refrains; communities are the protagonists, never decoration.

**Theme:** light · **Skins:** two (Marketing default · Platform audit-grade)

> Single source of truth for generating C-GEM screens in Google Stitch.
> Two skins, one core. Default to the **Marketing skin** unless the screen is a
> methodology doc, transparency dashboard, API surface, or live data feed — those
> use the **Platform skin** (see §8). Never mix the two on one screen.
>
> Sections §1–§9 are the authored spec. The reference sections below (Tokens,
> Components, Do's & Don'ts, Surfaces, Imagery, Layout, Motion, Agent Prompt Guide,
> Quick Start) are extracted from `colors_and_type.css`, `brand_book.css`, and
> `index.html` for machine use — they restate the same system in table form.

---

## 1. Visual Theme & Atmosphere

A grounded, editorial interface built for a non-profit that holds carbon and ecosystem
markets accountable on behalf of smallholder farming communities. The atmosphere is warm
and human but disciplined — closer to a field-research field notebook than a startup
landing page. Pure white ground, warm-leaning near-black ink, a single confident leaf
green. Sharp corners, hairline rules, generous negative space, and a triplet rhythm
that punctuates the page like a refrain.

Communities are the protagonists — never decoration, never "beneficiaries." Imagery and
copy treat farmers as principals. Data is presented in Indian numerals (lakh, crore,
1,00,000 format) with tabular figures, and every metric carries a real source and its
status (estimated / verified).

Calibration: **Density 4** (daily-app balanced — breathable, not sparse), **Variance 6**
(offset, asymmetric, left-aligned over centered), **Motion 5** (fluid, restrained spring
physics — directional fills and reveals, never decorative).

---

## 2. Color Palette & Roles

Pure white ground for both skins. One leaf-green primary. Accents are semantic and rare.

**Surface**
- **Paper** (#FFFFFF) — primary page ground. Never cream, never off-white as the base.
- **Warm Tonal** (#F6F7F2) — section-break band, subtle warmth.
- **Whisper Mute** (#FAFAF7) — almost-white alternate surface.
- **Card Surface** (#F4F4EF) — chip and card fill in tonal contexts.

**Ink**
- **Warm Ink** (#0E1410) — primary text, a warm-leaning near-black. Never pure `#000000` in the marketing skin.
- **Soft Ink** (#555555) — secondary text, descriptions, metadata.
- **Faint Ink** (#888888) — footnotes, captions, attribution.
- **Hairline** (#E8E8E6) — default 1px structural lines and borders.
- **Strong Hairline** (#CFD1CA) — emphasized dividers.

**Brand — Leaf scale**
- **Primary Leaf** (#2C7A3D) — the brand green. CTAs, links, active states, focus rings, eyebrows.
- **Press Leaf** (#1F5A2C) — hover and pressed states, directional button fills.
- **Deep Leaf** (#14361B) — darkest leaf for high-contrast moments.
- **Mid Leaf** (#459A55) / **Soft Leaf** (#8FC796) / **Pale Leaf** (#D8ECDC) / **Tint Leaf** (#ECF5EE) — supporting steps for fills and washes.

**Accents — semantic, used sparingly**
- **Sprout** (#C8F47A) — marketing-skin data highlight and text selection. The signature inline-highlight color.
- **Clay** (#B85829) — Beyond Carbon™ programme accent.
- **Harvest** (#C98A1F) — Carbon Ready™ programme accent, also the warning color.
- **Signal** (#FF7A3A) — urgent alerts only. Rare.
- **Sky** (#3A5FA8) — EEF statutory stamp only. Do not use as a general accent.
- **Danger** (#C1392E) — destructive / error.

Programme accent map (single source of truth): Carbon Ready™ → Harvest · Carbon Bridge™ → Ink · Climate Learn™ → Primary Leaf · Beyond Carbon™ → Clay.

Constraints: max one accent in play per composition beyond the leaf primary. No purple/blue neon. No oversaturated fills. No warm/cool gray drift — stay on this one neutral set.

---

## 3. Typography Rules

Self-hosted variable fonts. The marketing skin pairs a modern grotesque with an italic
literary serif used *only* for voice; the platform skin swaps to a sharper grotesque and
mono (see §8).

**Marketing skin (default)**
- **Display / Headlines:** **Geist** — weight 500, track-tight (-0.025em to -0.035em), line-height 0.93–1.05. Hierarchy comes from weight, color, and tracking, not from screaming size. Headlines balance-wrapped.
- **Body:** **Geist** — line-height 1.65, soft-ink color, max 60–65 characters per line.
- **Voice (community quotes, ledes, emphasis):** **Newsreader Italic** in Voice Leaf (#265e30 / `--leaf-700`) — used sparingly for the human voice. This is the one place serif is allowed, and only this distinctive italic.
- **Data / Mono / Meta / Eyebrows / Footnotes:** **Geist Mono** — uppercase, tracked (0.06em–0.12em), Primary Leaf for eyebrows, faint ink for footnotes.

**Stat / metric treatment:** Geist 500, tabular figures, tracking -0.035em, Indian numerals. The unit renders in small Newsreader italic leaf green. Numbers always tabular and keep-all (no mid-number wrap).

**Type scale (clamp-driven):** Mega cover `clamp(56px,9vw,144px)` · Display/hero `clamp(48px,6.5vw,96px)` · H1 `clamp(36px,4.5vw,64px)` · H2 `clamp(30px,3.6vw,48px)` · H3 24px · H4 20px · Lede 18px · Body 16px · Small 14px · Micro 12px · Mono 11px.

**Banned:** `Inter`. Generic serifs (`Times New Roman`, `Georgia`, `Garamond`, `Palatino`) as a face — Newsreader Italic is the only serif and only for voice. No serif in the platform skin at all. Gradient text on large headers.

---

## 4. Component Stylings

- **Buttons:** Flat, sharp-cornered (radius 4px marketing / 0 platform), no outer glow. Tactile `scale(0.97) translateY(1px)` on active. Primary = ink fill with a leaf-green directional wipe sliding in on hover (left-to-right). Secondary = ink outline with a bottom-up ink fill on hover. Leaf = leaf fill with a left-origin darken on hover. Ghost = text only, turns leaf on hover. One primary CTA per section.
- **Chips / Tags:** Pill (marketing) or square (platform), mono uppercase 11px, 1px ink border. Leaf and filled-ink variants available.
- **Cards:** White fill, 1px hairline border, radius 8px, generous 32px padding. Use only when elevation serves hierarchy; in dense contexts replace with border-top dividers and negative space. Ink-inverted variant uses sprout-colored eyebrows.
- **Index list:** Mono-numbered three-column grid (`56px 1fr auto`) with hairline row rules — the canonical way to present an ordered set in both skins.
- **Inputs:** Label above, helper optional, error text below. Leaf focus ring (`2px solid` Primary Leaf, 2px offset). No floating labels.
- **Loaders:** Skeletal shimmer matching exact layout dimensions. No circular spinners.
- **Empty states:** Composed compositions that show how to populate the data — not a bare "No data" line.
- **Shadows:** Minimal, warm-tinted (rgba(14,20,16,...)). Three steps only: 1px subtle, 16px diffused, 40px lifted. No hard or neon shadows.

---

## 5. Layout Principles

Grid-first, contained, asymmetric. Brushmark "C" logo may sit as a faint backdrop behind
hero or section zones — 6–10% opacity as a watermark, up to 12–14% as a centred voice
anchor (matches `.brushmark-bg` 7%, `.cover-section` 12%). Triplet rhythm ("Farmers First · Climate Always")
recurs as a mono-tracked refrain.

- No overlapping elements — every element owns a clean spatial zone. No absolute-positioned stacking of content.
- Centered hero layouts banned (variance 6) — use split-screen, left-aligned, or asymmetric whitespace.
- The generic "3 equal cards in a row" feature block is banned — use 2-column zig-zag, an asymmetric grid, the mono index-list, or horizontal scroll.
- CSS Grid over flexbox percentage math. Never `calc()` percentage hacks.
- Contain with a max-width (≈1200–1400px centered). Generous internal padding on a 4px spacing base (4 · 8 · 12 · 16 · 24 · 32 · 48 · 64 · 96 · 128).
- Full-height sections use `min-h-[100dvh]`, never `h-screen`.
- Sharp radii throughout (2/4/8/12px). Pill only for chips. Platform skin is fully square.

---

## 6. Responsive Rules

- **Mobile collapse (<768px):** every multi-column layout collapses to a single column. No exceptions.
- **No horizontal scroll** on mobile — overflow is a critical failure.
- **Typography:** headlines already scale via `clamp()`; body minimum 16px. Stats stay tabular and keep-all.
- **Touch targets:** minimum 44px.
- **Inline voice/imagery** stacks below the headline on mobile.
- **Navigation:** desktop horizontal nav collapses to a clean mobile menu.
- **Spacing:** vertical section gaps reduce proportionally, `clamp(3rem, 8vw, 6rem)`.

---

## 7. Motion & Interaction

- **Easing:** custom `cubic-bezier(0.22, 1, 0.36, 1)` (out) and `cubic-bezier(0.65, 0, 0.35, 1)` (in-out). Durations 140ms fast · 220ms base · 420ms slow. No linear easing.
- **Directional button fills** are the signature interaction — wipes and scales originating from a consistent edge, never a fade.
- **Staggered reveals:** cascade list and section entrances; never mount everything at once.
- **Restraint:** motion serves legibility and feedback, not spectacle. No perpetual decorative loops on marketing pages beyond the directional fills and text-selection sprout flash.
- **Performance:** animate `transform` and `opacity` only. Never `top`/`left`/`width`/`height`. Any grain/brushmark texture lives on a fixed pseudo-element at low opacity.

---

## 8. Platform Skin Override (audit-grade)

Apply when generating methodology docs, transparency dashboards, API surfaces, or live
project-data feeds. Same white ground, same leaf primary, same triplet rhythm — but
sharper and technical.

- **Ink → true black** (#000000). Hairlines sharpen to #D4D4D2.
- **Display & Body → Space Grotesk.** **Voice, Data, Meta → JetBrains Mono** — the voice goes technical (uppercase, tracked), not literary. No serif anywhere.
- **Data highlight & selection → Lime** (#B6F569) instead of Sprout.
- **All radii → 0.** Fully square corners, cards, chips, buttons.
- **Buttons lose directional fills** — flat instant color swaps only (black↔press-leaf, white↔black, lime↔soft-leaf). Square, mono, uppercase, tracked 0.08em.
- **Numbers:** monospace, tabular, Indian numerals — mandatory in this skin.

---

## 9. Anti-Patterns (Banned)

- No emojis anywhere.
- No `Inter`; no generic serif faces — Newsreader Italic is the only serif, voice-only, marketing skin only.
- No pure `#000000` in the marketing skin (use Warm Ink #0E1410); true black is platform-skin only.
- No purple/blue neon, no outer-glow or neon shadows, no oversaturated accents.
- No gradient text on large headers.
- No centered hero (this is a high-variance system).
- No "3 equal cards in a row" feature blocks.
- No overlapping elements — clean spatial separation always.
- No custom mouse cursors.
- No filler UI text: "Scroll to explore", "Swipe down", scroll arrows, bouncing chevrons.
- No AI copywriting clichés ("Elevate", "Seamless", "Unleash", "Next-Gen").
- **No "beneficiaries"** — say "communities" or "smallholder farmers." Farmers are protagonists who own, lead, negotiate, and earn — not recipients who "receive" or "benefit from."
- **No "gated" / "gate."** Pipeline access is *curated · open to selected/endorsed partners · earns its place* — never "the gate." Vetting is **360° due diligence on all parties**, never one-sided "we screen developers."
- **No money-position claims.** Never "no stake," "no cut," "we take nothing," or any gift-economy mechanics in public copy — these are internal-only and misleading in public.
- **Courses framing:** free to audit, certificate on login — never "all free," never a blanket "premium tier" or implication that lessons are paywalled.
- No vague environmental claims without backing data — every metric carries a **source and a status (estimated / verified)**.
- No Western numeral grouping for domestic figures — use Indian conventions (lakh, crore, 1,00,000).
- No generic placeholder names ("John Doe", "Acme", "Nexus") or fake round numbers (99.99%, 50%).
- No broken Unsplash links — use `picsum.photos` or SVG placeholders.

---

# Reference (extracted from source)

## Tokens — Colors

All values from `colors_and_type.css` (`:root`). Platform-skin overrides noted in the role column.

### Surface

| Name | Value | Token | Role |
|------|-------|-------|------|
| Paper | `#ffffff` | `--paper` | Primary page ground for both skins — never cream, never off-white as the base |
| Warm Tonal | `#f6f7f2` | `--paper-tonal` | Section-break band, subtle warmth; sidebar ground in the brand book |
| Whisper Mute | `#fafaf7` | `--paper-mute` | Almost-white alternate surface |
| Card Surface | `#f4f4ef` | `--paper-card` | Chip / card fill in tonal contexts, `.mono` chip background |

### Ink & Text

| Name | Value | Token | Role |
|------|-------|-------|------|
| Warm Ink | `#0e1410` | `--ink` | Primary text, headings — warm-leaning near-black. **Platform skin → `#000000`** |
| Strong Ink | `#1a1a1a` | `--ink-2` / `--line-ink` | Emphasis ink; platform-skin structural lines |
| Mute Ink | `#333333` | `--ink-mute` | Standard paragraph body color |
| Soft Ink | `#555555` | `--ink-soft` | Secondary text, descriptions, metadata |
| Faint Ink | `#888888` | `--ink-faint` | Footnotes, captions, attribution, idle nav items |
| Hairline | `#e8e8e6` | `--line` | Default 1px structural lines and borders. **Platform skin → `#d4d4d2`** |
| Strong Hairline | `#cfd1ca` | `--line-strong` | Emphasized dividers |

### Brand — Leaf scale

| Name | Value | Token | Role |
|------|-------|-------|------|
| Deep Leaf | `#14361b` | `--leaf-900` | Darkest leaf for high-contrast moments |
| Press Leaf | `#1f5a2c` | `--leaf-800` | Hover / pressed states, directional button fills |
| Voice Leaf | `#265e30` | `--leaf-700` | `.voice` italic color, chip-leaf text |
| Primary Leaf | `#2c7a3d` | `--leaf-600` | **The brand green.** CTAs, links, active states, focus rings, eyebrows |
| Mid Leaf | `#459a55` | `--leaf-500` | Supporting fills |
| Soft Leaf | `#8fc796` | `--leaf-300` | Washes, platform leaf-button hover |
| Pale Leaf | `#d8ecdc` | `--leaf-100` | Light washes |
| Tint Leaf | `#ecf5ee` | `--leaf-050` | Faintest leaf wash |

### Accents — semantic, rationed (max one per composition beyond the leaf primary)

| Name | Value | Token | Role |
|------|-------|-------|------|
| Sprout | `#c8f47a` | `--sprout` | Marketing-skin data highlight (`.hl`) and text selection — the signature inline highlight |
| Lime | `#b6f569` | `--lime` | Platform-skin data highlight and selection |
| Clay | `#b85829` | `--clay-600` | Beyond Carbon™ programme accent |
| Clay Soft | `#d27a45` | `--clay-500` | Supporting clay step |
| Harvest | `#c98a1f` | `--harvest` | Carbon Ready™ programme accent; also the warning color |
| Signal | `#ff7a3a` | `--signal` | Urgent alerts only — rare |
| Sky | `#3a5fa8` | `--sky` | EEF statutory stamp only; not a general accent |
| Danger | `#c1392e` | `--danger` | Destructive / error |

**Functional states:** success `--leaf-600` · warning `--harvest` · danger `#c1392e` · info `--sky`.

**Programme accent map (single source of truth, from `[data-programme]`):** Carbon Ready™ → Harvest · Carbon Bridge™ → Ink · Climate Learn™ → Primary Leaf · Beyond Carbon™ → Clay.

## Tokens — Typography

Self-hosted variable fonts via `@font-face`. Marketing skin defaults; platform-skin swaps in parentheses.

### Geist — Display & body (Marketing) · `--font-geist`
- **Substitute:** system-ui, -apple-system, Segoe UI, sans-serif
- **Weights:** 400 (body), 500 (all display & headings), 600 (nav active, swatch names), 700 (brand lockup)
- **Role:** All marketing headlines, body copy, and stats. Hierarchy comes from weight + color + tracking, not size. Headlines `text-wrap: balance`; body `text-wrap: pretty`.

### Newsreader Italic — Voice only (Marketing) · `--font-newsreader`
- **Substitute:** Georgia, Times New Roman, serif
- **Weight:** 400, always `font-style: italic`
- **Role:** The single permitted serif — community quotes, ledes, emphasis, and the italic stat unit. Renders in leaf green (`--leaf-700`). Never used for headlines or body.

### Geist Mono — Data / meta / eyebrows / footnotes (Marketing) · `--font-geist-mono`
- **Substitute:** ui-monospace, SF Mono, Menlo, monospace
- **Role:** Eyebrows (leaf, tracked 0.12em), footnotes (faint, 0.1em), triplet refrain, chips, index-list numbers, `.mono` code chips.

### Platform-skin families
- **Space Grotesk** (`--font-space-grotesk`) replaces Geist for display & body.
- **JetBrains Mono** (`--font-jetbrains-mono`) replaces both Newsreader (voice goes technical, uppercase, tracked — no serif) and Geist Mono (data, meta).

### Noto Sans Devanagari — Indian-script artefacts · `--font-devanagari`
- **Weight:** 600. Pairs with Geist via the `.deva` class. The triplet works in either script.

### Type Scale

| Role | Token | Size | Line Height | Letter Spacing |
|------|-------|------|-------------|----------------|
| mega (cover only) | `--fs-mega` | clamp(56px, 9vw, 144px) | 0.93 | -0.04em |
| display (hero) | `--fs-display` | clamp(48px, 6.5vw, 96px) | 0.93 | -0.035em |
| h1 | `--fs-h1` | clamp(36px, 4.5vw, 64px) | 1.05 | -0.025em |
| h2 | `--fs-h2` | clamp(30px, 3.6vw, 48px) | 1.05 | -0.02em |
| h3 | `--fs-h3` | 24px | 1.05 | -0.02em |
| h4 | `--fs-h4` | 20px | 1.05 | -0.02em |
| lede | `--fs-lede` | 18px | 1.5 | 0 |
| body | `--fs-body` | 16px | 1.65 | 0 |
| stat | `.stat` | clamp(34px, 4.4vw, 56px) | 1 | -0.035em (tabular, keep-all) |
| small | `--fs-small` | 14px | 1.5 | 0 |
| micro | `--fs-micro` | 12px | 1.5 | 0 |
| mono / eyebrow | `--fs-mono` | 11px | 1.5 | 0.06em–0.12em (uppercase) |

`font-feature-settings: "ss01" 1, "cv11" 1` on the root. Stats use `font-variant-numeric: tabular-nums` + `word-break: keep-all`, always in Indian numerals.

## Tokens — Spacing & Shapes

**Base unit:** 4px · **Density:** comfortable (calibration: Density 4)

### Spacing Scale

| Token | Value | Token | Value |
|-------|-------|-------|-------|
| `--space-1` | 4px | `--space-6` | 32px |
| `--space-2` | 8px | `--space-7` | 48px |
| `--space-3` | 12px | `--space-8` | 64px |
| `--space-4` | 16px | `--space-9` | 96px |
| `--space-5` | 24px | `--space-10` | 128px |

### Border Radius

| Token | Marketing | Platform |
|-------|-----------|----------|
| `--radius-sm` | 2px | 0 |
| `--radius-md` (buttons) | 4px | 0 |
| `--radius-lg` (cards) | 8px | 0 |
| `--radius-xl` | 12px | 0 |
| `--radius-pill` (chips) | 999px | 0 |

Platform skin is fully square — every radius collapses to 0.

### Shadows (minimal, warm-tinted `rgba(14,20,16,…)` — three steps only)

| Token | Value | Purpose |
|-------|-------|---------|
| `--shadow-1` | `0 1px 2px rgba(14,20,16,0.06)` | Subtle 1px lift |
| `--shadow-2` | `0 6px 16px rgba(14,20,16,0.08), 0 1px 2px rgba(14,20,16,0.04)` | Diffused hover elevation |
| `--shadow-3` | `0 18px 40px rgba(14,20,16,0.12)` | Lifted / modal |

### Layout
- **Content max-width:** ~1100–1400px (`.main-content` caps at 1100px; marketing screens 1200–1400px)
- **Sidebar (brand book):** 280px fixed (`--sidebar-width`), collapses below 960px
- **Section vertical rhythm:** `--space-8`/`--space-10` (64–128px); responsive `clamp(3rem, 8vw, 6rem)`
- **Card padding:** 32px (`--space-6`)
- **Element gap:** 8–16px

## Components

### Primary Button (`.btn--primary`)
**Role:** Highest-emphasis CTA — one per section.
Ink fill (`--ink`), paper text, radius 4px, padding 14px 22px, Geist 500 / 15px. A `::before` leaf-green panel (`--leaf-800`) wipes in left-to-right (`translateX(-101%) → 0`, 0.36s) on hover. Active: `scale(0.97) translateY(1px)`. **Platform:** square, JetBrains Mono uppercase 13px tracked 0.08em, no wipe — instant black↔press-leaf swap.

### Secondary Button (`.btn--secondary`)
**Role:** Supporting action beside the primary.
Transparent fill, ink outline + text. Bottom-up ink fill (`translateY(101%) → 0`) on hover; text flips to paper. **Platform:** white↔black instant swap, 1.5px black border.

### Leaf Button (`.btn--leaf`)
**Role:** On-brand action where green reads as affirmative.
Leaf fill (`--leaf-600`), paper text. Left-origin darken (`scaleX(0) → 1`, origin left) to `--leaf-800` on hover. **Platform:** lime↔soft-leaf instant swap.

### Ghost Button (`.btn--ghost`)
**Role:** Low-emphasis inline action. Text only, no border; turns leaf green on hover.

### Chip / Tag (`.chip`)
**Role:** Metadata label, programme tag, status.
Geist Mono uppercase 11px tracked 0.08em, 1px ink border, pill radius, padding 5px 10px. Variants: `.chip--leaf` (leaf text + border), `.chip--filled` (ink fill, paper text). **Platform:** square.

### Card (`.card`)
**Role:** Content container when elevation serves hierarchy.
Paper fill, 1px hairline border, radius 8px, 32px padding. `.card--ink` inverts to ink fill with sprout-colored eyebrows. A `.card[data-programme="…"]` gains a 3px accent left-border and fills its inner `.chip` with the programme accent. In dense contexts, replace with border-top dividers + negative space rather than stacking cards. **Platform:** square, ink border.

### Index List (`.index-list`)
**Role:** The canonical ordered set in both skins — replaces the banned "3 equal cards" block.
Three-column grid `56px 1fr auto`, hairline row rules (`border-top`/`border-bottom` 1px line), 14px rows. Number (`.ix`) in Geist Mono 11px uppercase tracked 0.1em, leaf green.

### Stat (`.stat`)
**Role:** Headline metric — always backed by a source.
Geist 500, clamp(34–56px), tabular-nums, tracking -0.035em, `word-break: keep-all`, Indian numerals. Unit (`.stat .unit`) in small Newsreader italic leaf green (platform: JetBrains Mono uppercase, soft ink).

### Triplet (`.triplet`)
**Role:** Brand refrain — "Farmers First · Climate Always".
Geist Mono 11px uppercase tracked 0.12em, ink. Items separated by 4px leaf-green dots via `::after` (last child suppressed).

### Eyebrow (`.eyebrow`)
**Role:** Section label above headlines. Geist Mono 11px uppercase tracked 0.12em, leaf green, weight 500.

### Voice (`.voice`)
**Role:** Human voice — community quotes, ledes, emphasis.
Newsreader italic, leaf green (`--leaf-700`), line-height 1.4. **Platform:** JetBrains Mono uppercase tracked 0.06em, ink — technical, not literary.

### Sidebar Navigation (`.sidebar` / `.nav-item`)
**Role:** Brand-book / docs left nav. 280px fixed, tonal ground, hairline right border. Idle links faint ink 14px; hover shifts color + indents `padding-left 16→20px`. Active: ink, 15px, weight 600, 2px leaf left-border. **Platform:** mono uppercase, ink-fill active state with lime text + 3px lime left-border. Collapses to full-width below 960px.

### Swatch Card (`.swatch-card`)
**Role:** Color documentation tile. 1px hairline border, radius 8px, 100px color block over details (name 14px/600, hex in mono with copy button, contrast badge on tonal ground). **Platform:** square, ink border.

### Inputs
Label above, helper optional, error below. Global leaf focus ring via `:focus-visible` — `2px solid var(--leaf-600)`, 2px offset. No floating labels.

## Do's and Don'ts

### Do
- Use **Warm Ink `#0e1410`** on **Paper `#ffffff`** as the default contrast pair in the marketing skin — reserve true black for the platform skin only.
- Reserve **Primary Leaf `#2c7a3d`** for CTAs, links, active states, eyebrows, and focus rings — it is the single brand accent.
- Build emphasis with the directional button fills (wipe / scale-from-edge) — they are the signature interaction, never a fade.
- Present every figure in **Indian numerals** (lakh, crore, 1,00,000) with tabular figures, and attach a backing source to each metric.
- Use the **mono index-list** or a 2-column zig-zag for ordered/feature sets instead of equal card rows.
- Switch the entire technical surface by toggling the `.platform-skin` class — same ground, same leaf, sharper everything.
- Keep one accent in play per composition beyond the leaf primary; let negative space and hairlines carry structure.
- Wrap one emphasis word per headline in `.hl` (sprout / lime) when a highlight is warranted — sparingly.

### Don't
- Don't use pure `#000000` in the marketing skin — that's a platform-skin signal.
- Don't say **"beneficiaries"** — communities and smallholder farmers are protagonists, named as such (they own, lead, negotiate, earn).
- Don't say **"gated" / "gate"** for pipeline access, and don't make money-position claims ("no stake," "no cut") — access is *curated / open to endorsed partners*; the financial model is internal-only.
- Don't center the hero or use "3 equal cards in a row" — this is a high-variance (V6), left-aligned system.
- Don't introduce `Inter` or a generic serif face — Newsreader Italic is the only serif, voice-only, marketing-only.
- Don't use gradient text on headers, neon/outer-glow shadows, oversaturated accents, or purple/blue neon.
- Don't recolour, crop, stretch, or skew the brushmark; don't substitute it for the logomark. Minimum 80px digital / 18mm print.
- Don't overlap elements or absolutely stack content — every element owns a clean spatial zone.
- Don't use Western numeral grouping for domestic figures, emojis, custom cursors, or filler scroll cues.

## Surfaces

| Level | Name | Value | Purpose |
|-------|------|-------|---------|
| 0 | Paper | `#ffffff` | Page ground — pure white for both skins |
| 1 | Warm Tonal | `#f6f7f2` | Section-break band, sidebar ground — subtle warmth against paper |
| 2 | Whisper Mute | `#fafaf7` | Almost-white alternate surface for nested zones |
| 3 | Card Surface | `#f4f4ef` | Chip / `.mono` chip / tonal card fill |
| 4 | Ink Stage | `#0e1410` (`#000` platform) | Inverted `.card--ink` and dark bands — sprout/lime eyebrows, maximum contrast |

## Elevation

Elevation is carried by **color value and hairline borders first, shadow second**. Cards separate from the ground via a 1px hairline (`--line`) and an 8px radius, not a drop shadow. When elevation is genuinely needed, only the three warm-tinted steps (`--shadow-1/2/3`) apply — 1px subtle, 16px diffused, 40px lifted. No hard, neon, or outer-glow shadows. In dense layouts, prefer border-top dividers and negative space over stacked elevated cards. The platform skin removes radius entirely, so separation there is pure hairline-on-white.

## Imagery

Two layers, both protagonist-first. **Photography** is real field documentation — farmer field schools, paddy transplanting, cotton-grower couples, groundnut harvest, aerial landscapes — farmers shown as principals at work, never staged "beneficiary" portraits, never stock lifestyle. **Illustration** is a sketch set (ambassador, female-farmer, onboard, negotiate, handhold, corner decoration) used as light editorial marks, not hero imagery. The **brushmark "C"** is a standalone identity element with three sanctioned roles: hero watermark at 6–10% opacity, centred voice anchor at 14% on paper-tonal, and a cap-x-height inline nav icon — always green, never recoloured or cropped. The logo system ships six cuts (Stacked, Logomark, Horizontal, Horizontal Alt, Textmark, Brushmark); use Full Colour on white/paper only, White or Inverse on dark and photographic surfaces. Placeholders use `picsum.photos` or SVG — never broken Unsplash links.

## Layout

Grid-first, contained, asymmetric. CSS Grid over flexbox percentage math — no `calc()` percentage hacks. Content contained at ~1100–1400px. The brand-book reference uses a fixed 280px left sidebar over a tonal ground with a hairline right border and a 1100px-capped main column; marketing screens drop the sidebar for a horizontal nav with a typographic active state. Hero layouts are **left-aligned or split-screen — never centered** (variance 6). Feature sets use 2-column zig-zag, asymmetric grids, the mono index-list, or horizontal scroll — never equal card rows. Section breaks are made by surface-value shifts (paper → warm-tonal) and hairline rules, punctuated by the triplet refrain. Full-height sections use `min-h-[100dvh]`, never `h-screen`. Below 768px every multi-column grid collapses to one column with zero horizontal overflow; touch targets stay ≥44px.

## Motion System

Custom easing only — `cubic-bezier(0.22, 1, 0.36, 1)` (out) and `cubic-bezier(0.65, 0, 0.35, 1)` (in-out); directional fills use `cubic-bezier(0.16, 1, 0.3, 1)`. Durations: 140ms fast (hover/feedback) · 220ms base · 420ms slow (directional wipes, reveals). No linear easing. The signature is the **directional button fill** — wipes and scales originating from a consistent edge, never a fade — plus staggered list/section reveals that never mount all at once, and the sprout/lime text-selection flash. Motion serves legibility and feedback, not spectacle: no perpetual decorative loops on marketing pages. Performance discipline — animate `transform` and `opacity` only, never `top`/`left`/`width`/`height`; grain or brushmark texture lives on a fixed low-opacity pseudo-element.

## Agent Prompt Guide

**Quick color reference**
- Page ground: `#ffffff` · Section band: `#f6f7f2`
- Primary text / headlines: `#0e1410` (platform: `#000000`)
- Secondary text: `#555555` · Footnotes: `#888888`
- Brand accent (CTA, links, active, eyebrows): `#2c7a3d` · hover/press: `#1f5a2c`
- Inline highlight: `#c8f47a` sprout (platform: `#b6f569` lime)
- Hairline: `#e8e8e6` (platform: `#d4d4d2`)

**Example component prompts**

1. **Hero (marketing):** Left-aligned, background `#ffffff`. Eyebrow in Geist Mono 11px uppercase tracked 0.12em, color `#2c7a3d`. Headline in Geist weight 500 at clamp(48px,6.5vw,96px), color `#0e1410`, letter-spacing -0.035em, line-height 0.93, balance-wrapped, one word wrapped in a sprout `#c8f47a` inline highlight. Newsreader-italic leaf-green lede beneath. One primary button: ink fill `#0e1410`, paper text, radius 4px, with a leaf-green `#1f5a2c` panel wiping in left-to-right on hover. Faint brushmark watermark at 7% behind. No centered layout.

2. **Project-transparency block:** A mono-numbered index list (grid `56px 1fr auto`, hairline row rules) — not cards. Number column in Geist Mono 11px uppercase leaf green. Each row carries a `.stat` value: Geist 500, tabular figures, Indian numerals (e.g. 1,24,500), with a small italic leaf-green unit. Every metric labelled with its source.

3. **Platform methodology page:** Add `.platform-skin`. True-black `#000000` ink on `#ffffff`, Space Grotesk headings and body, JetBrains Mono for data and labels (voice goes uppercase, tracked — no serif). All corners square (radius 0). Lime `#b6f569` data highlights. Flat buttons with instant color swaps (black↔`#1f5a2c`), JetBrains Mono uppercase tracked 0.08em. Hairlines at `#d4d4d2`.

4. **Programme card:** Set `data-programme="ready|bridge|learn|beyond"` to pull the accent (Harvest / Ink / Leaf / Clay) into `--programme-accent`. This also renders a **3px accent left-border** on the card and fills any `.chip` inside it with the accent (accent fill, paper text). Card on paper, 1px hairline, radius 8px, 32px padding. Eyebrow in the programme accent; the trademark (Carbon Ready™ etc.) spelled with the ™.

5. **Section with triplet refrain:** Surface-value section break (`#f6f7f2` band), hairline top rule, and the triplet "Farmers First · Climate Always" in Geist Mono 11px uppercase tracked 0.12em with 4px leaf-green dot separators.

## Similar Brands

- **The New York Times / editorial mastheads** — hairline rules, mono labels, and a serif reserved strictly for voice over a grotesque body.
- **Patagonia / environmental nonprofits** — subject-first documentary photography of people at work, restrained single-accent palette, evidence over decoration.
- **Stripe docs / Linear** — two-register systems (warm marketing vs. sharp technical) sharing one token core, switched by a skin class.
- **Field-research and audit publications** — tabular figures, sourced metrics, and a disciplined neutral palette that reads as accountability, not marketing.

## Quick Start

### CSS Custom Properties

```css
:root {
  /* Surface */
  --paper:        #ffffff;
  --paper-tonal:  #f6f7f2;
  --paper-mute:   #fafaf7;
  --paper-card:   #f4f4ef;

  /* Ink */
  --ink:          #0e1410;   /* marketing near-black */
  --ink-2:        #1a1a1a;
  --ink-mute:     #333333;
  --ink-soft:     #555555;
  --ink-faint:    #888888;
  --line:         #e8e8e6;
  --line-strong:  #cfd1ca;
  --line-ink:     #1a1a1a;

  /* Brand · Leaf scale */
  --leaf-900:     #14361b;
  --leaf-800:     #1f5a2c;   /* hover / press */
  --leaf-700:     #265e30;
  --leaf-600:     #2c7a3d;   /* PRIMARY brand green */
  --leaf-500:     #459a55;
  --leaf-300:     #8fc796;
  --leaf-100:     #d8ecdc;
  --leaf-050:     #ecf5ee;

  /* Accents */
  --sprout:       #c8f47a;   /* marketing data highlight */
  --lime:         #b6f569;   /* platform data highlight */
  --clay-600:     #b85829;
  --clay-500:     #d27a45;
  --signal:       #ff7a3a;
  --harvest:      #c98a1f;
  --sky:          #3a5fa8;

  /* Semantic */
  --success: var(--leaf-600);
  --warning: var(--harvest);
  --danger:  #c1392e;
  --info:    var(--sky);

  /* Type families — marketing defaults */
  --font-geist:          'Geist', system-ui, -apple-system, 'Segoe UI', sans-serif;
  --font-newsreader:     'Newsreader', Georgia, 'Times New Roman', serif;
  --font-geist-mono:     'Geist Mono', ui-monospace, 'SF Mono', Menlo, monospace;
  --font-space-grotesk:  'Space Grotesk', system-ui, sans-serif;
  --font-jetbrains-mono: 'JetBrains Mono', ui-monospace, 'SF Mono', Menlo, monospace;
  --font-devanagari:     'Noto Sans Devanagari', sans-serif;
  --font-display: var(--font-geist);
  --font-body:    var(--font-geist);
  --font-voice:   var(--font-newsreader);
  --font-data:    var(--font-geist-mono);
  --font-meta:    var(--font-geist-mono);
  --accent-data:  var(--sprout);

  /* Display scale */
  --fs-mega:    clamp(56px, 9vw, 144px);
  --fs-display: clamp(48px, 6.5vw, 96px);
  --fs-h1:      clamp(36px, 4.5vw, 64px);
  --fs-h2:      clamp(30px, 3.6vw, 48px);
  --fs-h3: 24px; --fs-h4: 20px; --fs-lede: 18px;
  --fs-body: 16px; --fs-small: 14px; --fs-micro: 12px; --fs-mono: 11px;

  --lh-tight: 0.93; --lh-snug: 1.05; --lh-normal: 1.5; --lh-loose: 1.65;
  --tracking-tight: -0.04em; --tracking-display: -0.035em;
  --tracking-h1: -0.025em; --tracking-h2: -0.02em;
  --tracking-mono: 0.06em; --tracking-eyebrow: 0.12em;

  /* Spacing (4px base) */
  --space-1: 4px;  --space-2: 8px;  --space-3: 12px;  --space-4: 16px;
  --space-5: 24px; --space-6: 32px; --space-7: 48px;  --space-8: 64px;
  --space-9: 96px; --space-10: 128px;

  /* Radii */
  --radius-sm: 2px; --radius-md: 4px; --radius-lg: 8px;
  --radius-xl: 12px; --radius-pill: 999px;

  /* Shadows (warm-tinted) */
  --shadow-1: 0 1px 2px rgba(14,20,16,0.06);
  --shadow-2: 0 6px 16px rgba(14,20,16,0.08), 0 1px 2px rgba(14,20,16,0.04);
  --shadow-3: 0 18px 40px rgba(14,20,16,0.12);

  /* Motion */
  --ease:     cubic-bezier(0.22, 1, 0.36, 1);
  --ease-in:  cubic-bezier(0.65, 0, 0.35, 1);
  --dur-fast: 140ms; --dur: 220ms; --dur-slow: 420ms;
}

/* Platform skin — audit-grade override */
.platform-skin {
  --font-display: var(--font-space-grotesk);
  --font-body:    var(--font-space-grotesk);
  --font-voice:   var(--font-jetbrains-mono);
  --font-data:    var(--font-jetbrains-mono);
  --font-meta:    var(--font-jetbrains-mono);
  --accent-data:  var(--lime);
  --ink:  #000000;
  --line: #d4d4d2;
  --line-ink: #000000;
  --radius-sm: 0; --radius-md: 0; --radius-lg: 0; --radius-xl: 0;
}
```

### Tailwind v4

```css
@theme {
  --color-paper: #ffffff;
  --color-paper-tonal: #f6f7f2;
  --color-paper-mute: #fafaf7;
  --color-paper-card: #f4f4ef;
  --color-ink: #0e1410;
  --color-ink-mute: #333333;
  --color-ink-soft: #555555;
  --color-ink-faint: #888888;
  --color-line: #e8e8e6;
  --color-line-strong: #cfd1ca;
  --color-leaf-900: #14361b;
  --color-leaf-800: #1f5a2c;
  --color-leaf-700: #265e30;
  --color-leaf-600: #2c7a3d;
  --color-leaf-500: #459a55;
  --color-leaf-300: #8fc796;
  --color-leaf-100: #d8ecdc;
  --color-leaf-050: #ecf5ee;
  --color-sprout: #c8f47a;
  --color-lime: #b6f569;
  --color-clay: #b85829;
  --color-harvest: #c98a1f;
  --color-signal: #ff7a3a;
  --color-sky: #3a5fa8;
  --color-danger: #c1392e;

  --font-display: 'Geist', system-ui, sans-serif;
  --font-body: 'Geist', system-ui, sans-serif;
  --font-voice: 'Newsreader', Georgia, serif;
  --font-mono: 'Geist Mono', ui-monospace, monospace;

  --text-mega: clamp(56px, 9vw, 144px);
  --text-display: clamp(48px, 6.5vw, 96px);
  --text-h1: clamp(36px, 4.5vw, 64px);
  --text-h2: clamp(30px, 3.6vw, 48px);
  --text-h3: 24px;
  --text-h4: 20px;
  --text-lede: 18px;
  --text-body: 16px;
  --text-small: 14px;
  --text-micro: 12px;
  --text-mono: 11px;

  --spacing-1: 4px;  --spacing-2: 8px;  --spacing-3: 12px; --spacing-4: 16px;
  --spacing-5: 24px; --spacing-6: 32px; --spacing-7: 48px; --spacing-8: 64px;
  --spacing-9: 96px; --spacing-10: 128px;

  --radius-sm: 2px; --radius-md: 4px; --radius-lg: 8px;
  --radius-xl: 12px; --radius-pill: 999px;

  --ease: cubic-bezier(0.22, 1, 0.36, 1);
  --ease-in: cubic-bezier(0.65, 0, 0.35, 1);
}
```
