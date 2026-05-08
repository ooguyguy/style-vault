# Design — style-vault

> Inventory snapshot · 2026-05-07 · Step 1 of portfolio design overhaul

## Surface

**Meta-design-system folder.** Per its own CLAUDE.md, this is "a curated collection of visual style profiles — designs Guy admires, analyzed forensically using the visual-style-forensics skill." The repo is *also* a Claude Code plugin (`.claude-plugin/plugin.json`) exposing `/analyze`, `/styles`, and `/the-way-of-code` commands.

Surface (visual artifacts) consists of profile-specific screenshots — currently `profiles/the-way-of-code/screenshots/*.png` (6 PNGs). The repo authors no first-party HTML/CSS — every hex/font in here is *cited from a third-party source being analyzed*, never proposed as design.

Surface counts: 0 HTML, 0 CSS, 0 SVG, 6 PNG (corpus screenshots), 0 PDF, 0 MJML.

Profiles present (`profiles/`):
- `the-way-of-code` — Rick Rubin / Tetragrammaton site (full forensic profile + 6 screenshots)
- `graphic-atlas` — Guy's own bible_system page profiled (no screenshots dir yet)

## Visual Tokens

This folder doesn't HAVE tokens — it CATALOGS them from other sources. The colors and fonts below are **cited findings** from each profile, not design choices made here.

### Colors — cited from `profiles/the-way-of-code/profile.md`

| Hex | Role (in source) | Cited from | Notes |
|---|---|---|---|
| `#FAF9F5` | Parchment bg (~70%) | `the-way-of-code/profile.md:43` | Warm cream — analogous to MarkCon V2 cream `#faf8f3` |
| `#1F1E1D` | Near-black ink | `the-way-of-code/profile.md:44` | Warm-shifted, never pure black |
| `#87867F` | Warm gray secondary | `the-way-of-code/profile.md:45` | |
| `#F0EEE6` | Artwork beige | `the-way-of-code/profile.md:46` | |
| `#D97757` | Terracotta (code line numbers only) | `the-way-of-code/profile.md:50` | Single chromatic accent |
| `#44A6E4` | Code blue (syntax only) | `the-way-of-code/profile.md:51` | |
| `#E8E6DC` | Deep beige | `the-way-of-code/profile.md:52` | |

### Colors — cited from `profiles/graphic-atlas/profile.md`

| Hex | Role | Cited from |
|---|---|---|
| `#F5EFE7` | Cream bg (~60%) | `graphic-atlas/profile.md:43` |
| `#FFFAF2` | Ivory surface | `graphic-atlas/profile.md:44` |
| `#2F2923` | Dark brown text | `graphic-atlas/profile.md:45` |
| `#9C7247` | Gold accent | `graphic-atlas/profile.md:46` |
| `#7B6148` | Gold-soft (mono labels) | `graphic-atlas/profile.md:47` |
| `#5B5147` | Text-dim | `graphic-atlas/profile.md:48` |
| `#458F95` | Cyan family marker | `graphic-atlas/profile.md:54` |
| `#9A5C79` | Magenta family marker | `graphic-atlas/profile.md:55` |
| `#4E6FA8` | Blue (meter only) | `graphic-atlas/profile.md:56` |
| `#628F58` | Green (meter only) | `graphic-atlas/profile.md:57` |
| `#B7773F` | Orange (rare) | `graphic-atlas/profile.md:58` |

### Typography — cited

| Font | Role (in source) | Cited from |
|---|---|---|
| Goudy Old Style | All copy at thewayofcode.com | `the-way-of-code/profile.md:79` |
| Courier Prime | Nav + code at thewayofcode.com | `the-way-of-code/profile.md:80` |
| Heebo | Hebrew body at graphic-atlas | `graphic-atlas/profile.md:88` |
| Cormorant Garamond | English display at graphic-atlas | `graphic-atlas/profile.md:89` |
| JetBrains Mono | UI labels at graphic-atlas | `graphic-atlas/profile.md:90` |

### Spacing / Radius / Shadow

Per-profile, not folder-wide. Profiles capture exact computed values (e.g., the-way-of-code documents 100px H1 with 54.92px letter-spacing and a φ scale ratio).

## Components & Patterns

### Source files
- `catalog.md` — master index (1 entry as of inventory)
- `tags.md` — tag taxonomy
- `profiles/{slug}/profile.md` — full forensic profile (10 sections per `README.md:51-61`)
- `profiles/{slug}/screenshots/` — corpus PNGs
- `commands/{name}.md` — slash commands (`analyze`, `styles`, `the-way-of-code`)
- `skills/the-way-of-code/SKILL.md` — Claude Code skill

### Recurring patterns
- Every profile uses YAML frontmatter (`name`, `source`, `creator`, `date_profiled`, `analysis`, `corpus_size`, `tags`)
- 10-section schema: First Impression DNA → Replication Rules
- "Scher Test" (would Paula Scher recognize this stripped of logo/text?) is a recurring qualitative gate
- Cross-modal sensory mapping (music / texture / temperature / weight) per profile

## Brand Voice & Writing Rules (design-adjacent)

- Repo voice in profiles is forensic + lyrical — Guy's analysis register, not JPSA register.
- Hard rule per `CLAUDE.md:24, 67`: **Never fabricate hex values.** Always extract via computed styles or eyedrop tools.
- Profiles are sources, not deliverables. Their palettes feed `design_ai_playbook` bible chapters as specimens.

## Audit Findings — Drift from JPSA System

**N/A — this is a catalog of OTHER systems, not a JPSA-affiliated design surface.** Drift detection on the cataloged palettes is not appropriate (the whole point is to capture diverse style DNA). The two profiles indexed both happen to live in the warm-paper / serif-or-mono family — neither is an anti-pattern hit:

- The Way of Code: monochrome warm parchment, no AI-dark, no purple, no mocha — clean.
- Graphic Atlas: cream-with-gold museum palette — by design, this IS a Guy/Bible-system aesthetic.

**Operational rule:** when AI agents propose adding profiles, ensure they don't auto-import an anti-pattern palette as a "neutral" reference. If a profile is added for, e.g., a purple/lavender SaaS UI, it must be tagged `anti-pattern-sample` so other agents can't pick it up as a recommendation.

## Lessons Learned (from past sessions in this folder)

- No `memory/` folder. Lessons are encoded into `CLAUDE.md` ("Never fabricate hex values"; "Screenshots should be optimized PNG, max 6-8 per profile").
- `catalog.md` only has 1 of N planned profiles indexed — the way-of-code. Graphic-atlas exists as `profile.md` but isn't yet listed. Operational gap.

## External Assets & Dependencies

- Plugin metadata: `.claude-plugin/plugin.json`
- Skill: `skills/the-way-of-code/SKILL.md`
- Downstream consumers: `design_ai_playbook` bible chapters import these profiles as specimens.
- No npm / pip dependencies.

---

*Source-of-truth files: `profiles/*/profile.md` (the actual content), `catalog.md` (index), `tags.md` (taxonomy), `CLAUDE.md` (no-fabrication rule). Anti-pattern definitions per `~/.claude/projects/.../memory/feedback_anti_palettes.md`.*
