# cgem-brand skill

Claude Code skill for generating fully on-brand content, components, and communications for **C-GEM** (Centre for Grower-centric Eco-value Mechanisms / Eco-Value Empowerment Foundation).

## Structure

```
cgem-brand/
├── SKILL.md                    Core skill — loaded on every C-GEM task
├── references/
│   ├── voice.md                Voice, tone, banned words, canonical phrases
│   ├── tokens.md               Full CSS token reference (colours, spacing, shadows)
│   ├── typography.md           Type scale, font loading, Devanagari, numeral rules
│   ├── assets.md               Asset inventory with file paths and usage rules
│   └── programmes.md           Four programme descriptions, accents, copy angles
└── templates/
    ├── marketing-page.html     Full marketing surface (hero, stats, programmes, CTA)
    ├── platform-dashboard.html Transparency/methodology surface (platform skin)
    ├── email-memo.html         Partnership memo / funder update
    └── slide-deck.html         Presentation (arrow-key navigation, both skins)
```

## Source

Brand assets and design tokens live in `d:\Antigravity Projects\Branding\`.
The canonical CSS is `colors_and_type.css`. All templates reference it.

## Usage

This skill triggers automatically in Claude Code whenever C-GEM work is requested.
To invoke manually: `/cgem-brand`
