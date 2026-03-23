# Style Vault

A curated collection of visual style profiles — designs Guy admires, analyzed forensically using the visual-style-forensics skill. Each profile is a complete DNA map: colors, typography, composition, texture, mood, and replication rules.

## Structure

```
style-vault/
├── profiles/              # One folder per style
│   └── {slug}/
│       ├── profile.md     # Full forensic style profile
│       ├── screenshots/   # Visual corpus (PNG)
│       └── tokens/        # Optional: CSS custom properties, Tailwind config
├── catalog.md             # Master index with thumbnails and tags
└── tags.md                # Tag taxonomy
```

## Conventions

- **Profile names are slugs:** `the-way-of-code`, `stripe-2024`, `muji-website`
- **Screenshots go in the profile folder** — max 6-8 per profile, optimized PNG
- **Every profile uses the visual-style-forensics skill** for consistency
- **Tags are from a controlled vocabulary** (see tags.md)
- **Never fabricate hex values** — extract from computed styles or eyedrop tools

## How to Add a Style

1. Run `/visual-style-forensics` on the source
2. Save the profile to `profiles/{slug}/profile.md`
3. Move screenshots to `profiles/{slug}/screenshots/`
4. Add entry to `catalog.md`
5. Tag it

## Commands

```bash
# This is a content repo -- no build step. Browse profiles directly:
cat profiles/the-way-of-code/profile.md

# List all profiles
ls profiles/

# List all tags
cat tags.md
```

## Profile Schema (profile.md)

Each profile uses YAML frontmatter followed by 10 analysis sections:
```yaml
---
name: "Display Name"
source: "https://..."
creator: "Designer / Studio"
date_profiled: YYYY-MM-DD
analysis: Full | Partial
corpus_size: "N views (description)"
tags: [tag1, tag2, ...]
---
```
**Sections:** 1. First Impression DNA, 2. Color System, 3. Typography, 4. Layout & Composition, 5. Texture & Surface, 6. Motion & Interaction, 7. Iconography & Illustration, 8. Photography & Media, 9. Mood & Atmosphere, 10. Replication Rules

## Gotchas

- This repo is also a **Claude Code plugin** (see `.claude-plugin/plugin.json`) -- `/analyze` and `/styles` commands are available
- Never fabricate hex values -- always extract from computed styles or eyedrop tools
- Screenshots should be optimized PNG, max 6-8 per profile

## Integration

- Profiles feed into `design_ai_playbook` bible chapters as specimens
- AI prompt translations (MJ, GPT-4o, Flux) live in each profile
- CSS tokens can be imported into projects directly
