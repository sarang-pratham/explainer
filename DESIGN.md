---
version: "alpha"
name: Technical Explainer
description: >
  Editorial-dense visual language for technical explainers. Draws from premium
  technical journalism — dense, confident, structured. Warm parchment surfaces,
  high-contrast ink, two semantic accent colors per document. Supports five
  layout modes: Comparison, Deep Dive, Process Flow, Taxonomy, Concept Card.
  Generators must vary the palette per topic while preserving all role
  relationships defined here.

colors:
  surface: "#F5F0E8"
  ink: "#1A1A1A"
  ink-secondary: "#4A4A4A"
  ink-muted: "#888888"
  accent-a: "#2D9E6B"
  accent-b: "#C44B2B"
  callout-warn-bg: "#FDECEA"
  callout-warn-border: "#E8A09A"
  callout-note-bg: "#E8F4F0"
  callout-note-border: "#7EC8B0"
  code-surface: "#EDE8DD"
  divider: "#D4CFC5"

typography:
  display:
    fontFamily: Source Serif 4
    fontSize: 2.4rem
    fontWeight: "900"
    lineHeight: "1.1"
    letterSpacing: -0.02em
  section-heading:
    fontFamily: Source Serif 4
    fontSize: 1.35rem
    fontWeight: "700"
    lineHeight: "1.2"
  body:
    fontFamily: Inter
    fontSize: 0.9rem
    fontWeight: "400"
    lineHeight: "1.65"
  code:
    fontFamily: JetBrains Mono
    fontSize: 0.8rem
    fontWeight: "400"
    lineHeight: "1.5"
  label:
    fontFamily: Inter
    fontSize: 0.62rem
    fontWeight: "700"
    letterSpacing: 0.09em
  step-number:
    fontFamily: JetBrains Mono
    fontSize: 0.72rem
    fontWeight: "700"
  flow-step-number:
    fontFamily: Source Serif 4
    fontSize: 2.5rem
    fontWeight: "900"
    lineHeight: "1"
  stat:
    fontFamily: Source Serif 4
    fontSize: 3.5rem
    fontWeight: "900"
    letterSpacing: -0.03em

rounded:
  none: 0px
  sm: 2px
  md: 4px
  lg: 8px

spacing:
  xs: 4px
  sm: 8px
  md: 16px
  lg: 24px
  xl: 40px
  xxl: 64px

components:
  tag-label:
    backgroundColor: "{colors.accent-a}"
    textColor: "#FFFFFF"
    rounded: "{rounded.sm}"
    padding: 2px 7px
    typography: "{typography.label}"
  tag-label-b:
    backgroundColor: "{colors.accent-b}"
    textColor: "#FFFFFF"
    rounded: "{rounded.sm}"
    padding: 2px 7px
    typography: "{typography.label}"
  callout-warn:
    backgroundColor: "{colors.callout-warn-bg}"
    textColor: "{colors.ink}"
    borderLeft: "3px solid {colors.callout-warn-border}"
    rounded: "{rounded.md}"
    padding: 12px 16px
  callout-note:
    backgroundColor: "{colors.callout-note-bg}"
    textColor: "{colors.ink}"
    borderLeft: "3px solid {colors.callout-note-border}"
    rounded: "{rounded.md}"
    padding: 12px 16px
  inline-code:
    backgroundColor: "{colors.code-surface}"
    textColor: "{colors.ink}"
    rounded: "{rounded.sm}"
    padding: 1px 5px
    typography: "{typography.code}"
  stat-callout:
    textColor: "{colors.accent-a}"
    typography: "{typography.stat}"
  stat-callout-b:
    textColor: "{colors.accent-b}"
    typography: "{typography.stat}"
  diagram-chip:
    size: 24px
    rounded: "{rounded.sm}"
    typography: "{typography.code}"
  diagram-chip-result:
    size: 28px
    rounded: "{rounded.sm}"
    typography: "{typography.code}"
---

## Overview

Technical Explainer is a visual language for explaining complex systems in a single scroll. The aesthetic comes from premium technical journalism — dense, confident, self-contained. Every explainer is complete on its own.

This design system supports five layout modes — Comparison, Deep Dive, Process Flow, Taxonomy, and Concept Card. All five share identical component tokens, color roles, and typographic rules. Only the structural grid changes.

**Palette flexibility rule.** The tokens above are the reference palette. Generators must derive a fresh palette for every topic, preserving the role relationships below.

## Colors

The palette is editorial and warm. Off-white surface grounds the composition — never pure white.

- **surface** — Warm parchment. Never #FFFFFF. Always tinted warm.
- **ink** — Near-black. All body text, headings, primary content.
- **ink-secondary** — Supporting text, secondary prose.
- **ink-muted** — Step numbers, row labels, diagram labels, hero-sub. ~50% lightness of ink.
- **accent-a** — Primary concept color. Left column (Comparison), concept heading (Deep Dive, Concept Card), first taxonomy item, flow step numbers, stat-a, tag labels, insight callout borders.
- **accent-b** — Secondary concept color. Right column (Comparison), outputs and results (all other modes), second taxonomy item, stat-b, warning callout borders.
- **callout-warn-bg / callout-warn-border** — Salmon-adjacent. Caveats, misconceptions, common errors.
- **callout-note-bg / callout-note-border** — Mint-adjacent. Counter-intuitive insights, surprising facts.
- **code-surface** — Slightly darker than surface. Background for inline code and table headers.
- **divider** — 1px separators. 20–30% darker than surface.

Never use more than two accent hues per explainer. In non-Comparison modes, accent-b marks outputs and results — it may be more analogous to accent-a (closer on the wheel) as long as perceptual contrast is clear.

## Typography

Three typeface roles, strictly separated:

- **Serif** (display, section-heading, flow-step-number, stat) — Source Serif 4. Headlines, large step numerals, stat numbers.
- **Sans** (body, label) — Inter. Prose and tag labels.
- **Mono** (code, step-number) — JetBrains Mono. Technical identifiers and step prefixes.

Never mix serif and sans within a paragraph. Inline code always uses mono. step-number and stat are the only places typeface families mix within a layout block.

## Layout

Single vertical scroll, max-width 880px, centered, on the surface color.

Shared structure across all modes: HERO → [MODE SECTIONS] → STAT ROW.

Mode-specific grids:
- Comparison — 50/50 two-column with 1px vertical divider. Optional bridge section. Comparison table.
- Deep Dive — Single column. 2–4 phase sections. Architecture callout at end.
- Process Flow — Single column. Flow steps with large serif numerals and ↓ arrows. Result section.
- Taxonomy — 2-column grid of items (single column if >4). When-to-use table.
- Concept Card — Single column. Definition + properties sections only.

## Elevation & Depth

No drop shadows anywhere. Depth from three tools only: 1px divider borders, callout background tints, and whitespace. Callout boxes use a 3px left border (accent-b for warns, accent-a for notes) plus the tinted background.

## Shapes

Sharp corners on all structural elements. Exceptions: inline-code and tag-label use rounded.sm (2px). Callouts use rounded.md (4px). Diagram chips use rounded.sm (2px).

## Components

**tag-label** — Colored chip above every h2. Uppercase, dot-separated keywords. accent-a background (tag-label) or accent-b background (tag-label-b).

**callout-warn** — Salmon background, 3px warn-border left border. Misconceptions, caveats, errors.

**callout-note** — Mint background, 3px note-border left border. Counter-intuitive insights, surprising facts.

**inline-code** — Monospace, code-surface background, 2px radius. Every technical identifier without exception.

**diagram-chip / diagram-chip-result** — 24px or 28px squares. accent-a fills for active states, opacity steps for older states, accent-b for result/output chips, dashed divider border for empty states.

**stat-callout / stat-callout-b** — Large stat numeral in accent-a or accent-b. One-line italic muted caption. Always in footer stat row.

## Do's and Don'ts

**Do:**
- Choose layout mode from the question type before writing any HTML.
- Apply accent-a and accent-b consistently throughout the entire document.
- Use 01, 02, 03 step numbers for all sequential explanations.
- Include at least one callout per section — alternate warn and note types.
- Include exactly one pull quote per section, in "…", italic.
- Apply inline-code to every technical identifier without exception.
- Include a stat row in every explainer.
- Generate a fresh palette per topic from the domain hue guidance in SKILL.md.

**Don't:**
- Never default to Comparison mode for a single-subject question.
- Never use box-shadow or any drop shadow.
- Never use #FFFFFF as a background.
- Never use more than two accent colors.
- Never write sequential steps as prose — numbered steps only.
- Never omit the tag label above a section heading.
- Never exceed 880px document width.
- Never reuse the reference palette tokens unchanged.