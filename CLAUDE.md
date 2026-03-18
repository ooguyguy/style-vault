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

## Integration

- Profiles feed into `design_ai_playbook` bible chapters as specimens
- AI prompt translations (MJ, GPT-4o, Flux) live in each profile
- CSS tokens can be imported into projects directly
