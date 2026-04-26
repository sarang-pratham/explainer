# Shared Components

These templates apply identically across all layout modes. Load this file when building any section.

---

## Tag Label

Placed directly above every `<h2>`. Never omit.

```html
<div class="tag">KEYWORD · SUBLABEL</div>       <!-- accent-a background -->
<div class="tag tag-b">KEYWORD · SUBLABEL</div>  <!-- accent-b background, for output/result sections -->
```

Content: UPPERCASE, dot-separated keywords. 2–3 keywords max. Examples: `PHASE 1 · ATTENTION`, `VECTORIZED · PARALLEL`, `OUTPUT · RESULT`.

---

## Numbered Steps

For any sequential process, mechanism breakdown, or list of properties. Always `01 02 03` — never bullet points.

```html
<ol class="steps">
  <li>
    <span class="step-num">01</span>
    <span><strong>Bold Label</strong> — explanation using <code>identifier</code> if needed.</span>
  </li>
  <li>
    <span class="step-num">02</span>
    <span><strong>Bold Label</strong> — explanation.</span>
  </li>
</ol>
```

3–5 steps per section. If a step is a formula or chain, write it as: `<code>unflatten → softmax → sum</code>`.

---

## Pull Quote

One per section. Captures the mechanism or insight in one plain-language sentence.

```html
<p class="pull-quote">"The mechanism or insight in one sentence."</p>
```

In curly double quotes `"…"`. Italic. No special background or border.

---

## Callout — Warning

For: misconceptions, caveats, common errors, "why it isn't X" nuances.

```html
<div class="callout callout-warn">
  <div class="callout-title">WHY IT ISN'T JUST X</div>
  <p>Explanation of the nuance or common mistake. 2–4 sentences. Italic.</p>
</div>
```

Title examples: `WHY IT ISN'T JUST RETRIEVAL`, `COMMON MISTAKE`, `THE GOTCHA`, `NOT THE SAME AS X`.

---

## Callout — Insight

For: counter-intuitive behaviors, surprising facts, non-obvious design decisions.

```html
<div class="callout callout-note">
  <div class="callout-title">COUNTER-INTUITIVE</div>
  <p>The surprising or non-obvious fact. 2–4 sentences. Italic.</p>
</div>
```

Title examples: `COUNTER-INTUITIVE`, `WHY THIS MATTERS`, `THE SURPRISING PART`, `NOT AN APPROXIMATION`.

Alternate between warn and note across sections — don't use the same type back-to-back.

---

## Diagram Chips

For: token sequences, buffer states, cache contents, sliding windows, before/after states. Use when the concept has clear discrete units moving through stages.

```html
<div class="diagram-label">LABEL DESCRIBING WHAT THIS SHOWS</div>
<div class="chip-row">
  <span class="chip" style="background:var(--accent-a)">t0</span>
  <span class="chip" style="background:var(--accent-a);opacity:.6">t1</span>
  <span class="chip chip-empty">t2</span>
  <span class="chip chip-empty">t3</span>
  <span class="arrow">→</span>
  <span class="chip chip-result" style="background:var(--accent-b)">KV</span>
</div>
```

- `chip`: 24×24px, filled, monospace label, color from accent
- `chip-empty`: transparent, dashed `divider` border, muted text — for "not yet filled" or "waiting" states
- `chip-result`: 28×28px, `accent-b` fill — for outputs, compressed entries, written results
- Opacity steps: `1.0 → 0.6 → 0.4` to show older/less-active states
- 4–8 chips per row, 2–4 rows max per diagram

Diagram label: UPPERCASE, letter-spaced, muted — e.g. `TOKEN STATE ACROSS 4 DECODE STEPS`.

---

## Stat Row

Always in the footer. Two quantitative anchors — one per concept, phase, or key dimension.

```html
<footer class="stat-row">
  <div class="stat-block">
    <div class="stat-number accent-a">4<span class="stat-unit">×</span></div>
    <div class="stat-label">one-line description of what this measures</div>
  </div>
  <div class="stat-center">
    <strong>Center phrase that</strong><br>
    <em>frames both stats together</em>
  </div>
  <div class="stat-block">
    <div class="stat-number accent-b">75<span class="stat-unit">%</span></div>
    <div class="stat-label">one-line description of what this measures</div>
  </div>
</footer>
```

Units: `×`, `%`, `ms`, `KB`, `×` — same font-size as numeral or slightly smaller. Stat label: 1 line max, italic, muted. Center text: optional, frames the relationship between the two numbers.

For non-Comparison modes: the two stats represent the two most important quantitative facts about the concept — not necessarily opposing values.

---

## Inline Code

Apply `<code>` to every:
- Function or method name: `softmax`, `wgate(x)`, `should_compress()`
- Variable or parameter: `start_pos`, `seqlen`, `kv_cache`
- Array or index access: `kv_cache[start_pos // 4]`
- Operator chain or pseudocode: `unflatten → softmax → sum`
- Boolean expression: `(start_pos + 1) % 4 == 0`
- Type or shape: `[chunks, ratio, dim]`, `(batch, heads, seq, dim)`
- Return values: `None`, `True`, `False`

Never style technical identifiers as plain text. No exceptions.