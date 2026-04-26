---
name: explainer
description: >
  Generate a self-contained, visually rich technical explainer as a single-file
  HTML document. Use for any request to explain, visualize, or break down a
  technical concept — comparisons, mechanisms, architectures, processes,
  taxonomies, or deep dives. Detects the right layout mode from the question.
  Read DESIGN.md for visual tokens. Read references/ files for layout and component templates.
license: MIT
compatibility: Outputs a standalone HTML file with inline CSS. Optional vanilla JS for interactive modes. Google Fonts via fonts.googleapis.com.
metadata:
  author: pratham
  version: "1.0"
---

# Technical Explainer

Generates editorial-style technical explainers as single-file HTML. The aesthetic is dense, confident, and self-contained — like a well-annotated technical magazine page.

## Before You Start

Read these files in order:
1. `DESIGN.md` — color tokens, typography roles, component rules
2. `references/LAYOUTS.md` — HTML structure for your chosen layout mode
3. `references/COMPONENTS.md` — shared section templates (steps, callouts, chips, table, stat row)
4. `references/CSS.md` — the full CSS block to paste into `<style>`

## Step 1 — Choose a Layout Mode

Match the question to exactly one mode. Never default to Comparison.

| Question pattern | Mode |
|---|---|
| "X vs Y", "compare X and Y", "difference between X and Y" | **comparison** |
| "how does X work", "explain X internally", "what happens inside X" | **deep-dive** |
| "what happens when", "walk me through", "how does X become Y" | **process-flow** |
| "types of X", "kinds of X", "spectrum of X" | **taxonomy** |
| "what is X" (short, introductory) | **concept-card** |

## Step 2 — Generate a Color Palette

Derive a fresh palette for this topic. Never reuse the DESIGN.md reference tokens verbatim.

Pick `accent-a` from the topic's domain feel:

| Domain | accent-a hue |
|---|---|
| Memory / cache / storage | teal, cyan |
| Computation / inference | purple, indigo |
| Networks / protocols | blue, slate |
| Performance / speed | amber, orange |
| Data structures / algorithms | green, emerald |
| Hardware / architecture | warm gray, burnt sienna |

- `accent-b`: ~150° away on the color wheel (complementary). In non-Comparison modes it marks outputs and results — it can be more analogous, just ensure clear perceptual contrast.
- `surface`: warm neutral, `hsl(40–50, 15–30%, 92–96%)`. Never `#FFFFFF`.
- Callout backgrounds: very desaturated, light versions of each accent.

## Step 3 — Extract the Content

Before writing any HTML, identify:

- The **3–5 core mechanisms or phases** that structure the explanation
- **One pull quote per section** — the mechanism in one plain-language sentence, in `"…"`
- **One callout per section** — alternate between warn (misconception) and note (insight)
- **Two memorable stats** — quantitative anchors for the footer stat row
- **Any sequences or states** that benefit from chip diagrams (token flows, buffer states, cache contents)

## Core Rules

- No `box-shadow` anywhere. Depth comes from borders and background tints only.
- No `#FFFFFF` background. Surface is always warm-tinted.
- No more than two accent colors per explainer.
- Sequential processes always use `01 02 03` numbered steps — never bullet points.
- Every `<h2>` must have a `<div class="tag">` directly above it.
- Every section needs at least one callout and one pull quote.
- All technical identifiers, variable names, function names → `<code>` inline.
- Max document width: 880px.
- Stat row always present — find two quantitative anchors for every explainer.
- Save one self-contained `.html` file with inline `<style>` only.