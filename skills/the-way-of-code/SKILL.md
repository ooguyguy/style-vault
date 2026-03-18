---
name: the-way-of-code
description: "Apply The Way of Code visual style — monastic minimalism with generative line art. Warm parchment, Goudy Old Style serif, extreme whitespace, monochrome palette. Use when building any visual deliverable (HTML, email, landing page, presentation, UI) in this style."
---

# Style: The Way of Code

You are now designing in The Way of Code style. Every HTML, CSS, email, landing page, component, or visual deliverable you create MUST follow these rules exactly. Do not deviate. Do not "improve." Do not add elements the style forbids.

**Source:** https://www.thewayofcode.com/ (Rick Rubin / Tetragrammaton)
**DNA:** Monastic. Algorithmic. Parchment.

---

## Colors — Use These Exact Values

```css
:root {
  --color-bg: #FAF9F5;              /* Parchment — page background */
  --color-text: #1F1E1D;            /* Near-black — headings, body text */
  --color-secondary: #87867F;       /* Warm gray — secondary text, captions */
  --color-surface: #F0EEE6;         /* Artwork beige — cards, containers */
  --color-surface-deep: #E8E6DC;    /* Deep beige — subtle variation */
  --color-accent: #D97757;          /* Terracotta — ONLY for code/accents, never body */
  --color-code-blue: #44A6E4;       /* Code blue — syntax highlighting only */
}
```

**Rules:**
- Background is ALWAYS `#FAF9F5`. Never pure white.
- Text is ALWAYS `#1F1E1D`. Never pure black.
- No saturated colors in the main design. Terracotta and blue are for code only.
- No gradients. No shadows. No colored backgrounds.

---

## Typography — Two Fonts Only

**Primary:** `goudy-old-style, Georgia, 'Times New Roman', serif`
**Secondary:** `'Courier Prime', 'Courier New', Courier, monospace`

No sans-serif. Ever.

### Hierarchy

| Level | Size | Weight | Letter-Spacing | Use |
|-------|------|--------|---------------|-----|
| H1 / Title | 80-100px | 400 (regular) | **50-55px** | Main title only |
| H2 / Subtitle | 48-62px | 400 | 1.5px | Subtitle, italic |
| H3 / Section | 28-32px | 400 | 1px | Section headers |
| Body | 20-22px | 400 | normal | Main content |
| Small / Nav | 14-16px | 400 | 0.8px | Navigation, captions |
| Code / Mono | 14-15px | 400 | normal | Code, technical labels |

**Scale ratio:** Golden ratio (1.618x) between levels.

**Rules:**
- Hierarchy through SIZE, not weight. Never use bold in body text.
- Italics are rare — subtitles only.
- Title letter-spacing of 50px+ is THE signature move. Do not skip it.
- All uppercase for H1 only.

---

## Layout

- **Content fills ~30-35% of the viewport.** The rest is void. This is non-negotiable.
- Two-column asymmetric when pairing image + text: visual left, text right.
- Single-column centered for titles and standalone content.
- Vertically center content — never start at the top of the page.
- Generous margins: 80px+ on sides, 120px+ top/bottom.

---

## Imagery

- **No photographs. No raster images.**
- Use SVG line drawings, generative patterns, or wireframe illustrations.
- All monochrome — thin dark strokes on `#F0EEE6` background.
- Organic-mathematical hybrids: parametric curves, mesh surfaces, computational geometry.
- If no illustration is available, use empty space instead. Void > stock art.

---

## What You Must NEVER Do

1. Never use sans-serif fonts
2. Never use bold weight for body text
3. Never use colored backgrounds (only parchment variants)
4. Never add borders, box-shadows, or visible containers
5. Never use icons or emoji
6. Never add decorative elements (dividers, ornaments, flourishes)
7. Never use photographs or raster images
8. Never use pure white (#FFFFFF) or pure black (#000000)
9. Never make navigation visually dominant
10. Never fill more than 40% of the viewport with content
11. Never use gradients
12. Never use multiple accent colors — one terracotta accent max, and only for code
13. Never center body text — left-align, ragged right
14. Never use bullet points or numbered lists in the main design (use line breaks and stanzas)

---

## Quick Reference — When Building

**An HTML page:** Parchment bg, Goudy Old Style, massive letter-spaced title, content centered in viewport with 65%+ whitespace, no nav chrome.

**An email:** Same parchment bg, Goudy fallback to Georgia, generous padding (60px+ sides), single-column, no buttons — use understated text links.

**A landing page:** Full-viewport hero with title only (50px+ tracking). Content sections below with extreme breathing room. SVG illustrations if available, otherwise pure typography.

**A component/card:** `#F0EEE6` background, no border, no shadow, no radius. Content with generous padding (40px+). Goudy Old Style text.

**A presentation slide:** One idea per slide. Parchment background. Title in upper-center with extreme tracking. Maximum 2-3 lines of body text. 60%+ empty space.
