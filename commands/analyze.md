---
description: "Analyze a new design and add it to the style vault. Usage: /styles:analyze <URL or path>"
argument-hint: "<URL or image path>"
allowed-tools:
  - Read
  - Write
  - Grep
  - Glob
  - WebFetch
  - WebSearch
  - AskUserQuestion
---

# /styles:analyze — Add a New Style to the Vault

Arguments: `$ARGUMENTS`

## Process

1. If no arguments, ask: "What URL or image should I analyze?"
2. Run the `visual-style-forensics` skill on the provided source
3. Ask the user for a slug name (e.g., `stripe-2024`, `muji-web`)
4. Save the profile to `${CLAUDE_PLUGIN_ROOT}/profiles/{slug}/profile.md`
5. Save screenshots to `${CLAUDE_PLUGIN_ROOT}/profiles/{slug}/screenshots/`
6. Create a new skill at `${CLAUDE_PLUGIN_ROOT}/skills/{slug}/SKILL.md` — extract the replication rules, colors, typography, and CSS tokens from the forensic profile into an immediately-applicable style skill (follow the format of existing skills in `/skills/`)
7. Create a shortcut command at `${CLAUDE_PLUGIN_ROOT}/commands/{slug}.md`
8. Update `${CLAUDE_PLUGIN_ROOT}/catalog.md` with the new entry
9. Announce: "Style '{name}' added to the vault. Use `/styles:{slug}` or `/{slug}` to apply it."
