# Layout Templates

HTML structure for each of the five layout modes. Use the skeleton that matches your chosen mode. Fill `[GENERATED]` palette values from your derived colors.

---

## Document Shell (all modes)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>[CONCEPT TITLE]</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Source+Serif+4:ital,wght@0,700;0,900;1,400&family=Inter:wght@400;600;700&family=JetBrains+Mono:wght@400;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --surface:            [GENERATED];
      --ink:                [GENERATED];
      --ink-muted:          [GENERATED];
      --accent-a:           [GENERATED];
      --accent-b:           [GENERATED];
      --callout-warn-bg:    [GENERATED];
      --callout-warn-border:[GENERATED];
      --callout-note-bg:    [GENERATED];
      --callout-note-border:[GENERATED];
      --code-surface:       [GENERATED];
      --divider:            [GENERATED];
      --font-serif: 'Source Serif 4', Georgia, serif;
      --font-sans:  'Inter', system-ui, sans-serif;
      --font-mono:  'JetBrains Mono', 'Courier New', monospace;
    }
    /* paste CSS.md contents here */
  </style>
</head>
<body>
  <!-- HERO (see hero variant for your mode below) -->
  <!-- MODE SECTIONS -->
  <!-- STAT ROW -->
</body>
</html>
```

---

## Mode: Comparison

Structure: `HERO → TWO COLUMNS → BRIDGE (optional) → TABLE → STAT ROW`

### Hero
```html
<header class="hero">
  <h1>
    <span class="accent-a">Term A</span>
    <span class="vs"> vs </span>
    <span class="accent-b">Term B</span>
  </h1>
  <p class="tagline">
    <strong>What they share.</strong>
    <em>What separates them. The core tension.</em>
  </p>
</header>
```

### Two-Column Section
```html
<section class="two-col">
  <div class="panel">
    <div class="tag">KEYWORD · SUBLABEL</div>
    <h2 class="accent-a">Concept A</h2>
    <p class="prose">Explanation. 2–4 sentences.</p>
    <!-- chip diagram if concept has state/sequence -->
    <p class="pull-quote">"Core mechanism in one sentence."</p>
    <!-- steps, callouts from COMPONENTS.md -->
  </div>
  <div class="col-divider"></div>
  <div class="panel">
    <div class="tag tag-b">KEYWORD · SUBLABEL</div>
    <h2 class="accent-b">Concept B</h2>
    <!-- mirror structure, accent-b throughout -->
  </div>
</section>
```

### Bridge Section (optional)
For behavior shared across both concepts — occurs at their boundary or interaction point.
```html
<section class="bridge">
  <hr>
  <div class="tag">SHARED MECHANISM · CONDITION</div>
  <h2>Bridge Heading</h2>
  <p class="prose">Shared behavior explanation.</p>
</section>
```

### Comparison Table
Always include. 5–8 rows.
```html
<section class="table-section">
  <div class="table-meta">SAME [SHARED PARAM] · DIFFERENT [DIMENSION]</div>
  <table class="comparison-table">
    <thead>
      <tr>
        <th></th>
        <th class="accent-a">Concept A</th>
        <th class="accent-b">Concept B</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="row-label">DIMENSION</td>
        <td>Value for A</td>
        <td>Value for B</td>
      </tr>
      <!-- 4–7 more rows -->
    </tbody>
    <tfoot>
      <tr><td colspan="3" class="shared-note">Shared behavior note — no seam.</td></tr>
    </tfoot>
  </table>
</section>
```

---

## Mode: Deep Dive

Structure: `HERO → OVERVIEW → PHASE SECTIONS (2–4) → DESIGN CALLOUT → STAT ROW`

Single concept, no comparison column. `accent-a` for primary annotation, `accent-b` for outputs and results.

### Hero
```html
<header class="hero">
  <h1 class="accent-a">Concept Name</h1>
  <div class="hero-sub">DOMAIN · CATEGORY</div>
  <p class="tagline">
    <strong>What it is.</strong>
    <em>Why it matters or what problem it solves.</em>
  </p>
</header>
```

### Phase Section
Repeat 2–4 times, one per phase/layer/sub-mechanism.
```html
<section class="phase-section">
  <div class="tag">PHASE N · LABEL</div>
  <h2>Phase Heading</h2>
  <p class="prose">What happens in this phase. 2–4 sentences.</p>
  <!-- chip diagram, steps, callouts from COMPONENTS.md -->
  <p class="pull-quote">"Core insight about this phase."</p>
</section>
<hr>
```

### Design Callout
After all phases — explains the key architectural decision behind the whole mechanism.
```html
<div class="callout callout-warn">
  <div class="callout-title">THE DESIGN DECISION</div>
  <p>Why this system is built this way. What alternatives exist and why they weren't chosen. 3–5 sentences.</p>
</div>
```

---

## Mode: Process Flow

Structure: `HERO → FLOW STEPS (sequential) → RESULT SECTION → STAT ROW`

Each step feeds the next. Large step numerals make the sequence the visual anchor.

### Hero
```html
<header class="hero">
  <h1>From <span class="accent-a">Input</span> to <span class="accent-b">Output</span></h1>
  <div class="hero-sub">PROCESS NAME · CONTEXT</div>
  <p class="tagline">
    <strong>What this process produces.</strong>
    <em>Why the order of steps matters.</em>
  </p>
</header>
```

### Flow Step
Repeat for each step. Separate with `<div class="flow-arrow">↓</div>`.
```html
<section class="flow-step">
  <div class="flow-step-num accent-a">01</div>
  <div class="flow-step-body">
    <div class="tag">STEP NAME · SUBLABEL</div>
    <h2>Step Heading</h2>
    <p class="prose">What happens. What state changes. 2–4 sentences.</p>
    <!-- chip diagram, steps, callouts from COMPONENTS.md -->
    <p class="pull-quote">"What this step produces."</p>
  </div>
</section>
<div class="flow-arrow">↓</div>
```

### Result Section
```html
<section class="result-section">
  <div class="tag tag-b">OUTPUT · RESULT</div>
  <h2 class="accent-b">What You Get</h2>
  <p class="prose">Description of the final output and its properties.</p>
  <!-- one callout-warn for the most common mistake -->
</section>
```

---

## Mode: Taxonomy

Structure: `HERO → TAXONOMY ITEMS (2-column grid) → WHEN-TO-USE TABLE → STAT ROW`

Each type/variant gets equal visual weight. Differentiate items with opacity steps of `accent-a` on their top border.

### Hero
```html
<header class="hero">
  <h1>The <span class="accent-a">Types of X</span></h1>
  <div class="hero-sub">TAXONOMY · N VARIANTS</div>
  <p class="tagline">
    <strong>What they all share.</strong>
    <em>What distinguishes each variant and when it appears.</em>
  </p>
</header>
```

### Taxonomy Grid
```html
<div class="taxonomy-grid">
  <section class="taxonomy-item" style="border-top-color: var(--accent-a);">
    <div class="tag">TYPE 1 · LABEL</div>
    <h2>Variant Name</h2>
    <p class="prose">What this variant is and what defines it.</p>
    <p class="pull-quote">"Defining characteristic."</p>
    <!-- steps, one callout -->
  </section>
  <section class="taxonomy-item" style="border-top-color: color-mix(in srgb, var(--accent-a) 70%, transparent);">
    <!-- Type 2, slightly desaturated border -->
  </section>
  <!-- continue at 50%, 40% opacity for types 3 and 4 -->
</div>
```

Use single column (`grid-template-columns: 1fr`) if more than 4 items.

### When-to-Use Table
Same structure as comparison table. Rows are situations/conditions. Columns are the taxonomy items.

---

## Mode: Concept Card

Structure: `HERO → DEFINITION → PROPERTIES → STAT ROW`

Compact. No comparison table. For short "what is X" questions.

### Hero
```html
<header class="hero">
  <h1 class="accent-a">Concept Name</h1>
  <div class="hero-sub">DOMAIN · CATEGORY</div>
  <p class="tagline"><em>Plain-language definition in one sentence.</em></p>
</header>
```

### Definition Section
```html
<section class="phase-section">
  <div class="tag">WHAT IT IS</div>
  <h2>Definition</h2>
  <p class="prose">What it is, what problem it solves, where it appears. 3–5 sentences.</p>
  <p class="pull-quote">"The intuition in one sentence."</p>
</section>
<hr>
```

### Properties Section
```html
<section class="phase-section">
  <div class="tag">HOW IT WORKS</div>
  <h2>Key Properties</h2>
  <!-- steps, one callout-warn, one callout-note -->
</section>
```