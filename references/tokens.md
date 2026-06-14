# C-GEM Design Tokens Reference

Import in any HTML artefact:
```html
<link rel="stylesheet" href="colors_and_type.css">
```

For platform skin, add class to body or container:
```html
<body class="platform-skin">
```

---

## Surface tokens

| Token | Value | Usage |
|-------|-------|-------|
| `--paper` | `#FFFFFF` | Page ground. The only background colour for pages. Never cream. |
| `--paper-tonal` | `#F6F7F2` | Warm-tinted off-white. Section breaks only. |
| `--paper-mute` | `#FAFAF7` | Almost white, subtle warmth. |
| `--paper-card` | `#F4F4EF` | Card and chip surfaces. |

## Ink tokens

| Token | Value | Usage |
|-------|-------|-------|
| `--ink` | `#0E1410` | Primary text — warm-leaning black. |
| `--ink-2` | `#1A1A1A` | |
| `--ink-mute` | `#333333` | Body paragraphs. |
| `--ink-soft` | `#555555` | Secondary text. |
| `--ink-faint` | `#888888` | Meta, footnotes. |
| `--line` | `#E8E8E6` | Default hairlines. |
| `--line-strong` | `#CFD1CA` | Stronger borders. |
| `--line-ink` | `#1A1A1A` | Platform skin borders. |

Platform skin override: `--ink` becomes `#000000` (true black).

## Leaf (brand green) scale

| Token | Value | Usage |
|-------|-------|-------|
| `--leaf-900` | `#14361B` | Darkest — rare |
| `--leaf-800` | `#1F5A2C` | Hover / press states |
| `--leaf-700` | `#265E30` | Voice text colour (`.voice` class) |
| `--leaf-600` | `#2C7A3D` | **PRIMARY brand green** — wordmark, eyebrows, primary buttons |
| `--leaf-500` | `#459A55` | Lighter green |
| `--leaf-300` | `#8FC796` | Tint |
| `--leaf-100` | `#D8ECDC` | Background tint |
| `--leaf-050` | `#ECF5EE` | Lightest tint |

## Accent tokens — sparing, semantic only

| Token | Value | Programme / Use |
|-------|-------|-----------------|
| `--sprout` | `#C8F47A` | Marketing-skin data highlight (shock of growth) |
| `--lime` | `#B6F569` | Platform-skin live data / chart highlight |
| `--clay-600` | `#B85829` | Beyond Carbon™ programme accent |
| `--clay-500` | `#D27A45` | |
| `--harvest` | `#C98A1F` | Carbon Ready™ accent |
| `--signal` | `#FF7A3A` | Alerts, urgent — use very rarely |
| `--sky` | `#3A5FA8` | **EEF statutory stamp ONLY. Never reuse elsewhere.** |

## Semantic tokens

```css
--success:  var(--leaf-600)
--warning:  var(--harvest)
--danger:   #c1392e
--info:     var(--sky)
```

## Programme accent map

```css
[data-programme="ready"]  { --programme-accent: var(--harvest); }
[data-programme="bridge"] { --programme-accent: var(--ink); }
[data-programme="learn"]  { --programme-accent: var(--leaf-600); }
[data-programme="beyond"] { --programme-accent: var(--clay-600); }
```

---

## Spacing scale (4px base)

| Token | Value |
|-------|-------|
| `--space-1` | 4px |
| `--space-2` | 8px |
| `--space-3` | 12px |
| `--space-4` | 16px |
| `--space-5` | 24px |
| `--space-6` | 32px |
| `--space-7` | 48px |
| `--space-8` | 64px |
| `--space-9` | 96px |
| `--space-10` | 128px |

Section padding clamps from 56–128px. Max content width 1320px. Max line length 60ch.

## Radii

| Token | Marketing skin | Platform skin |
|-------|----------------|---------------|
| `--radius-sm` | 2px | 0 |
| `--radius-md` | 4px | 0 |
| `--radius-lg` | 8px | 0 |
| `--radius-xl` | 12px | 0 |
| `--radius-pill` | 999px | — |

Platform skin: **0 corners everywhere.** Pure rectangles.

## Shadows (minimal, warm-tinted)

```css
--shadow-1: 0 1px 2px rgba(14, 20, 16, 0.06);
--shadow-2: 0 6px 16px rgba(14, 20, 16, 0.08), 0 1px 2px rgba(14, 20, 16, 0.04);
--shadow-3: 0 18px 40px rgba(14, 20, 16, 0.12);
```

Most surfaces use 1px borders, not shadows. Shadows reserved for modals and lifted hover states.

## Motion

```css
--ease:     cubic-bezier(0.22, 1, 0.36, 1)
--ease-in:  cubic-bezier(0.65, 0, 0.35, 1)
--dur-fast: 140ms
--dur:      220ms
--dur-slow: 420ms
```

Hover: colour shift to leaf-600. No scale, no bounce. Press: 1px translateY + slight darken.

---

## Avoid entirely

Cream, beige, sage, burgundy, maroon, terracotta-as-primary, pure cool grey, gradients that aren't earth-tone, bluish-purple, heavy drop shadows as decoration.
