# cgem-brand

Claude Code skill for generating fully on-brand content, components, and communications for **C-GEM** (Centre for Grower-centric Eco-value Mechanisms / Eco-Value Empowerment Foundation).

## Installation

Copy this `brand_skill/` folder to `~/.claude/skills/cgem-brand/` (Mac/Linux) or `%USERPROFILE%\.claude\skills\cgem-brand\` (Windows), then restart Claude Code.

```
cp -r brand_skill/ ~/.claude/skills/cgem-brand
```

Once installed, use `/cgem-brand` to invoke it manually, or it will trigger automatically on C-GEM tasks.

## Structure

```
brand_skill/
├── SKILL.md                      Core skill instructions
├── README.md                     This file
├── colors_and_type.css           The design system stylesheet — every template links to it;
│                                 defines all tokens and type-role classes (.voice, .triplet, .stat, …)
├── DESIGN.md                     Standalone Google Stitch design spec (for Stitch screen generation;
│                                 not part of the content-generation load path)
├── evals/
│   └── evals.json                Test prompts for skill evaluation
├── references/
│   ├── voice.md                  Voice, tone, banned words, canonical phrases
│   ├── tokens.md                 Full CSS token reference (colours, spacing, shadows)
│   ├── typography.md             Type scale, font loading, Devanagari, numeral rules
│   ├── assets.md                 Asset inventory with relative paths and usage rules
│   └── programmes.md             Four programme descriptions, accents, copy angles
├── templates/
│   ├── marketing-page.html       Full marketing surface (hero, stats, programmes, CTA)
│   ├── platform-dashboard.html   Transparency/methodology surface (platform skin)
│   ├── email-memo.html           Partnership memo / funder update
│   └── slide-deck.html           Presentation (arrow-key navigation, both skins)
└── assets/
    ├── logos/                    All logo variants (horizontal, stacked, logomark, textmark) in
    │                             black/white/colour/inverse — plus logo-brushmark.png, the primary brushmark C
    ├── illustrations/            Warm sketch illustrations for section breaks and pull-quotes
    ├── photography/              Documentary field photography, farmers as protagonists
    └── fonts/                    Variable woff2 fonts (Geist, Newsreader, Space Grotesk, JetBrains Mono, Noto Devanagari)
```

## What it covers

- Marketing pages and landing surfaces
- Programme communications (Carbon Ready™ / Carbon Bridge™ / Climate Learn™ / Beyond Carbon™)
- Partnership memos and funder updates
- Transparency dashboards (platform skin)
- Slide decks and internal presentations
- Social posts, field updates, annual report copy
- HTML component generation using the C-GEM design system

Voice: grounded, rights-based, farmers as protagonists — never beneficiaries.
