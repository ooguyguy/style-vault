# Style Vault

A curated collection of forensic visual style profiles -- designs admired, analyzed with precision. Each profile is a complete DNA map: colors, typography, composition, texture, mood, and replication rules.

This is a public repo. No build step -- browse profiles directly.

## What's Here

- **profiles/** -- One folder per style (e.g., `the-way-of-code`, `graphic-atlas`), each containing a full forensic analysis, screenshots, and optional design tokens
- **commands/** -- Claude Code slash commands (`/analyze`, `/styles`) for running style forensics
- **skills/** -- Reusable skill definitions for visual style analysis
- **catalog.md** -- Master index of all profiled styles
- **tags.md** -- Controlled tag taxonomy

## How It Works

Profiles are generated using the `visual-style-forensics` skill and follow a 10-section schema: First Impression DNA, Color System, Typography, Layout, Texture, Motion, Iconography, Photography, Mood, and Replication Rules.

## Usage

```bash
ls profiles/                          # List all profiled styles
cat profiles/the-way-of-code/profile.md   # Read a profile
```
