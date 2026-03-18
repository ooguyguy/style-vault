---
description: "Load a visual style and apply it to everything you build. Usage: /styles {style-name}"
argument-hint: "<style-name> — e.g., the-way-of-code"
allowed-tools:
  - Read
  - Grep
  - Glob
  - AskUserQuestion
---

# /styles — Apply a Visual Style

Arguments: `$ARGUMENTS`

## If No Arguments

Use AskUserQuestion to let the user pick from available styles:

First, scan `${CLAUDE_PLUGIN_ROOT}/skills/` for all directories — each one is an available style.

Present the list:
> "Which style do you want to apply?"
> - {list each style name}

## If Arguments Provided

1. Parse the first argument as the style name (lowercase, hyphenated)
2. Check alias table:

| Alias | Canonical |
|-------|-----------|
| wayofcode, way-of-code, rubin | the-way-of-code |

3. Read `${CLAUDE_PLUGIN_ROOT}/skills/{style-name}/SKILL.md`
4. If not found, say: "Style '{style-name}' not in the vault. Run /styles:analyze on a URL to add it."
5. If found, load the skill. Announce:

> **Style loaded: {Style Name}**
> Everything I build from now on follows this style. Give me something to design.

The style is now active. Apply it to all visual output for the rest of the conversation.
