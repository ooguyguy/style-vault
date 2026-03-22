---
name: Graphic Atlas
source: bible_system/graphic-atlas.html (Design AI Playbook)
creator: Guy Edasis + Claude
date_profiled: 2026-03-21
analysis: Full
corpus_size: 1 page (14 sections, ~600 lines HTML)
tags: [editorial, museum, bilingual, hebrew, warm-neutral, sans-dominant, mono-accent, paper-texture, scholarly, cultural]
---

# Visual Style Profile: Graphic Atlas

**Source:** `bible_system/graphic-atlas.html` (Design AI Playbook repo)
**Corpus:** 1 page, 14 sections, shared.css design system
**Analysis:** Full | **Date:** 2026-03-21
**Workflow:** Second Creative Lab `/style-analysis` run (SV-2026-001)

---

## 1. First Impression DNA (The Blink)

A warm museum exhibition catalog for graphic design — the page feels like walking through a curated gallery where the walls are made of parchment and the labels are printed in gold. This is not a website — it's an exhibition. The dominant feeling is scholarly warmth: authoritative but inviting, like a well-lit library run by someone with taste.

**3 Keywords:** Museum. Scholarly. Warm.

**Scher Test: PASS.** The combination of Hebrew RTL body text, English monospace uppercase labels with wide tracking, gold-on-cream palette, and paper-grain texture overlay is instantly recognizable. No other design bible page looks like this — the bilingual code-switch IS the identity.

**Cross-modal:**
- Music: Nils Frahm's *All Melody* — warm, layered, precise, inviting
- Texture: Heavy cotton stock paper, warm to the touch, with visible fiber at the edge
- Temperature: Late afternoon in a European design museum — warm spotlights, cool ambient
- Weight: Substantial but not heavy. Curated, not accumulated.

---

## 2. Color System

### Primary Palette

| Swatch | Hex | RGB | Proportion | Usage |
|--------|-----|-----|-----------|-------|
| Cream (bg) | `#F5EFE7` | 245,239,231 | ~60% | Page background — the dominant "material" |
| Ivory (surface) | `#FFFAF2` | 255,250,242 | ~20% | Card/panel fill — elevated surfaces |
| Dark Brown (text) | `#2F2923` | 47,41,35 | ~10% | Primary text — never pure black |
| Gold (accent) | `#9C7247` | 156,114,71 | ~5% | Threading accent — kickers, gradients, links |
| Gold-soft (label) | `#7B6148` | 123,97,72 | ~3% | Monospace labels, nav text |
| Text-dim | `#5B5147` | 91,81,71 | ~2% | Secondary text (descriptions, lede) |

### Secondary Palette

| Swatch | Hex | RGB | Usage |
|--------|-----|-----|-------|
| Cyan | `#458F95` | 69,143,149 | System/Order family marker — muted |
| Magenta | `#9A5C79` | 154,92,121 | Culture/Signature family marker — muted |
| Blue | `#4E6FA8` | 78,111,168 | Meter fills only |
| Green | `#628F58` | 98,143,88 | Meter fills only |
| Orange | `#B7773F` | 183,119,63 | Secondary accent — rare |

### Color Relationships
- **Zero-gray rule.** Every neutral in the palette is warm brown-based. No pure gray exists anywhere — not in text, not in shadows, not in borders.
- **Gold threads everything.** The primary accent `#9C7247` appears in the hero h1 gradient, kicker text, chip borders, nav hover states, and card shadows.
- **Borders are gold-tinted translucent:** `rgba(126,100,68,0.18)` — never solid gray lines.
- **Shadows are warm brown:** `rgba(92,74,52,0.08)` — never blue or gray shadow cast.
- Contrast: Dark Brown on Cream = ~11.2:1 (exceeds AAA).

### Color Grammar
- Body text = dark brown on cream. Always.
- System labels = gold-soft monospace uppercase. Always.
- Cards = ivory surface with gold-tinted border and warm brown shadow.
- Accents are semantic: cyan = System/Order, magenta = Culture/Signature.
- Room system cycles background temperature: cream (default) → white (room-white) → dark (room-dark).

### Forbidden Colors
- No pure white `#FFFFFF` — always warm cream minimum.
- No pure black `#000000` — always warm dark brown `#2F2923`.
- No gray shadows — always warm brown-tinted.
- No cool blue tones in backgrounds or text.
- Cyan and magenta are always MUTED — never saturated.

---

## 3. Typography System

### Typeface DNA

| Role | Font | Class | Usage |
|------|------|-------|-------|
| Primary (Hebrew body) | **Heebo** | Neo-grotesque sans-serif | Body text, headings, all Hebrew content. Variable weight 300-900. |
| Secondary (English display) | **Cormorant Garamond** | Garalde serif | English display text, blockquotes. Weights 400-700. |
| System (labels/UI) | **JetBrains Mono** | Monospace | Kickers, micro labels, chips, section numbers, nav, table headers. |

### Type Scale

| Element | Size | Weight | Line-height | Letter-spacing |
|---------|------|--------|-------------|----------------|
| Hero H1 | clamp(3rem, 5.8vw, 8rem) | 900 | 1.08 | -0.03em |
| Section H2 | ~2rem | 800 | 1.18 | -0.03em |
| Card H3 | 1.34rem | 700 | 1.18 | -0.03em |
| Body | 18px | 400 | 1.78 | normal |
| Lede/hero p | 1.17rem | 400 | 1.78 | normal |
| System labels | 0.74-0.82rem | 400 | normal | 0.14-0.24em |
| Chips | 0.76rem | 400 | normal | normal |

### Typography Grammar
- **Hebrew headings:** 1.18 minimum line-height (flat ceiling geometry needs more air than Latin).
- **Hero H1 override:** 1.08 line-height (tighter for display impact — English hero only).
- **English labels:** Always uppercase + tracked (0.14-0.24em). Creates "specimen label" effect.
- **Hebrew body:** Normal case, normal tracking. Hierarchy via size/weight only (no case system).
- **The bilingual code-switch:** Hebrew body text with English monospace labels is not a compromise — it IS the visual identity.
- **H1 gradient:** `linear-gradient(135deg, #2F2923 0%, #9C7247 78%)` with background-clip text.
- **Negative tracking on display:** -0.03em for h1-h4 (tightens Hebrew flat-ceiling geometry at display sizes).

---

## 4. Composition & Layout

### Grid System
- **Max-width:** 1360px centered, 14px margins.
- **Section formula:** `.number` (mono, gold) → `h2` (Hebrew, heavy) → `p` (description, dim) → content grid.
- **Card grids:** 1.2rem gap, auto-fill responsive (`minmax(280-320px, 1fr)`).
- **Hero:** 2-column `1.1fr / 0.9fr` (text + image board).
- **Gallery room:** Full-width figure + adjacent copy block.

### Room-Temperature Rhythm
Sections cycle through background temperatures:
```
cream → cream → cream → cream → cream → cream →
white (Section 07) → cream → cream →
dark (Section 10) → cream →
white (Section 12) → cream → cream
```
This creates an architectural experience — like moving between gallery rooms with different lighting.

### Spacing Grammar
- **Macro:** Sections separated by `.divider` elements.
- **Card padding:** 1.15rem.
- **Card radius:** 22px (radius-lg).
- **Inline image radius:** 14px.
- **Pills/chips:** 999px (fully rounded).

---

## 5. Texture & Surface

### Paper Grain
SVG fractalNoise overlay, baseFrequency 0.8, 3 octaves, 18% opacity, fixed position, multiply blend mode. Creates subtle paper-like grain across the entire page without being heavy.

### Radial Light Pools
Two radial gradients on body:
- Gold-tinted at position 14% 10% (upper left warmth)
- Cyan-tinted at position 84% 16% (upper right cool)
Creates gentle warm/cool light variation.

### Card Surfaces
Linear gradient from `rgba(255,250,242,0.97)` to `rgba(246,238,228,0.99)` — cards are slightly warmer than background.

### Nav Blur
`backdrop-filter: blur(18px)` with 86% opacity warm cream. Frosted glass effect, always warm.

---

## 6. Imagery

- **Format:** WebP, lazy loaded (except hero: eager).
- **Treatment:** `object-fit: cover`, 14px border-radius.
- **CSS specimens:** When photos unavailable, CSS-generated abstract specimens (animated scribbles, panel layouts).
- **Alt text:** Descriptive with intent — not just "image" but "Editorial specimen showing quiet authority through typography and pacing."
- **Subject matter:** Design specimens, style comparisons, proof sheets — never stock photos, never decorative.

---

## 7. Distinctive Signatures

1. **Bilingual code-switch as identity.** Hebrew body text with English monospace labels isn't a compromise — it's the visual signature. The JetBrains Mono labels create a "specimen label" effect against Hebrew prose.
2. **Gold-on-parchment temperature.** Every color is warm. No pure grays, no cool neutrals, no blue shadows. The atmosphere is "library/archive" without a single bookshelf image.
3. **Room-temperature rhythm.** Sections cycle cream → white → dark, creating exhibition-like "rooms" where background shifts as you scroll. Architectural, not decorative.

---

## 8. Historical Lineage

- **Museum exhibition design** — section numbering, gallery-room layout, specimen frames, "room" temperature system.
- **Contemporary editorial magazines** — *Kinfolk*, *Apartamento*, *Monocle* — generous whitespace, serif/sans pairing.
- **Israeli bilingual design tradition** — Heebo + English labels, RTL-first with LTR annotations.
- **Design systems documentation** — meters, decision tools, structured cards (Storybook, Figma tokens) — but warmer.
- **Art book typography** — negative letter-spacing on headings, gradient text fills, monospace annotations.

---

## 9. Replication Rules

### Do
- Start with warm cream background (`#F5EFE7`) — never white.
- Use Heebo for Hebrew, Cormorant Garamond for English display, JetBrains Mono for system labels.
- Thread gold (`#9C7247`) through everything — borders, accents, gradients, labels.
- Add paper grain overlay (SVG noise, 18% opacity, multiply blend).
- Use warm brown shadows — never gray or blue.
- Cycle room temperatures across sections for architectural rhythm.

### Never
- Use pure white, pure black, or any gray without brown undertone.
- Use glossy surfaces, glass, or reflective materials.
- Set Hebrew headings below 1.18 line-height.
- Use stock photos or decorative imagery.
- Use cyan or magenta at full saturation — always muted.
- Skip the monospace label system — it's load-bearing, not decorative.
