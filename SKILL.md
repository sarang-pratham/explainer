---
name: explainer
description: >
  Generate a technical explainer as a .mdx file for any concept, system,
  mechanism, architecture, algorithm, comparison, or research idea. Trigger
  for requests to "explain", "visualize", "break down", or "create an explainer".
  The .mdx is compiled by explainer-compile into a styled interactive dashboard.
---

# Explainer Skill

Write a single `.mdx` file. The file is compiled by **explainer-compile** — you do not control styling, colors, or fonts. Your job is to choose the right components, structure content clearly, and pass accurate data through props.

Once the file is written, Run:

```
npx @sarang-pratham/explainer-compile build ./<filename>.mdx --open
```

---

# Step 1 — Preference Elicitation

**Before generating anything, ask the user these preference knobs using your internal question tool to gather their answers.** If they already specified some in their request, skip those. If they say "just go ahead" or "use defaults", proceed immediately with defaults.

| Knob       | Options                                                                               | Default    |
| ---------- | ------------------------------------------------------------------------------------- | ---------- |
| `length`   | `brief` (2–3 sections) · `standard` (4–6) · `deep` (7–10)                             | `standard` |
| `density`  | `compact` (tight, minimal prose) · `balanced` · `spacious` (expansive, detailed)      | `balanced` |
| `tone`     | `neutral` (pure explanation) · `opinionated` (adds thesis, personal take, conclusion) | `neutral`  |
| `diagrams` | `none` · `minimal` (1 diagram) · `rich` (2–3 diagrams)                                | `minimal`  |

**Understand the Content**

Extract before writing:

- Core concept
- Natural sections
- What each section _is_ - process, comparison, data, system loop → pick component
- Quantitative anchors
- Flow or cycle?
- Strong take or conclusion?

---

## Step 2 — Compose the MDX

Read the relevant references file before composing:

- `references/layout-primitives.md` — wrappers, grids, steps, tabs
- `references/data-primitives.md` — metrics, arrays, stacks, charts
- `references/diagram-primitives.md` — pipelines, system loops, tree views
- `references/editorial-primitives.md` — callouts, hero stats, inline markers
- `references/variants.md` — semantic color variants

**Every document must have:**

- `<Dashboard>` wrapper with `title` and `subtitle`
- At least one `<StepSection>` anchoring the narrative
- A closing `<EditorialCallout>` or `<HeroStat>` as the takeaway

**Composition rules:**

- Do not use the same component back to back
- Layout containers are greedy (fill available space)
- Data primitives are intrinsic (never stretch)
- `<Marker>` and `<Badge>` can appear inline within prose

---

## Hard Rules

- No inline styles, no hex colors, no CSS — the compiler owns all visuals
- No raw HTML — MDX components only
- Technical terms always use backtick inline `code` in prose
- The output filename is chosen contextually — never hardcode `explanation.mdx`
- **Use pure Markdown for prose, NOT HTML tags.** Use `#`, `*`, `**`, `-`, and backticks instead of `<h1>`, `<p>`, `<ul>`, `<strong>`, etc.
- No raw HTML for structural blocks (use MDX components instead)
- Create the .mdx file in the **current workspace**
- **Do NOT** write import statements for components. All primitive components are globally injected and available by default.
- **Do NOT** write metadata headers
- **NO SQUEEZING DIAGRAMS:** Do NOT nest horizontal flow diagrams natively requiring large widths.
- **STRICT JS OBJECT SYNTAX IN PROPS:** When passing attributes to diagram components.
- **USE SPATIAL BREAKS (BLANK LINES):** leave at least one empty line between every component and text block in the .mdx file.
