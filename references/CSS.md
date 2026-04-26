# CSS Reference

Paste this into the `<style>` block inside the document shell from `LAYOUTS.md`. Fill `:root` variables with your generated palette before pasting.

```css
/* ─── Reset ─────────────────────────────────────────── */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

/* ─── Base ───────────────────────────────────────────── */
body {
  background: var(--surface);
  color: var(--ink);
  font-family: var(--font-sans);
  font-size: 15px;
  line-height: 1.65;
  max-width: 880px;
  margin: 0 auto;
  padding: 40px 24px 64px;
}
h1 {
  font-family: var(--font-serif);
  font-weight: 900;
  font-size: 2.4rem;
  line-height: 1.1;
  letter-spacing: -0.02em;
}
h2 {
  font-family: var(--font-serif);
  font-weight: 700;
  font-size: 1.35rem;
  line-height: 1.2;
  margin-bottom: 10px;
}
p { margin-bottom: 10px; }
hr { border: none; border-top: 1px solid var(--divider); margin: 32px 0; }
code {
  font-family: var(--font-mono);
  font-size: .8em;
  background: var(--code-surface);
  padding: 1px 5px;
  border-radius: 2px;
}

/* ─── Accent colors ──────────────────────────────────── */
.accent-a { color: var(--accent-a); }
.accent-b { color: var(--accent-b); }

/* ─── Hero ───────────────────────────────────────────── */
.hero {
  padding-bottom: 20px;
  border-bottom: 1px solid var(--divider);
  margin-bottom: 28px;
}
.hero .vs { color: var(--ink-muted); }
.hero-sub {
  font-family: var(--font-mono);
  font-size: .62rem;
  font-weight: 700;
  letter-spacing: .09em;
  text-transform: uppercase;
  color: var(--ink-muted);
  margin: 8px 0;
}
.tagline { margin-top: 8px; font-size: .95rem; }

/* ─── Tag label ──────────────────────────────────────── */
.tag {
  display: inline-block;
  font-family: var(--font-sans);
  font-size: .62rem;
  font-weight: 700;
  letter-spacing: .09em;
  text-transform: uppercase;
  background: var(--accent-a);
  color: #fff;
  padding: 2px 7px;
  border-radius: 2px;
  margin-bottom: 10px;
}
.tag-b { background: var(--accent-b); }

/* ─── Comparison: two-column ─────────────────────────── */
.two-col {
  display: grid;
  grid-template-columns: 1fr 1px 1fr;
  gap: 0 28px;
  border-top: 1px solid var(--divider);
  padding-top: 28px;
  margin-top: 28px;
}
.col-divider { background: var(--divider); }

/* ─── Deep Dive / Concept Card: phase sections ───────── */
.phase-section {
  margin-top: 28px;
  padding-top: 28px;
  border-top: 1px solid var(--divider);
}

/* ─── Process Flow ───────────────────────────────────── */
.flow-step {
  display: grid;
  grid-template-columns: 48px 1fr;
  gap: 0 20px;
  margin-top: 28px;
  padding-top: 28px;
  border-top: 1px solid var(--divider);
}
.flow-step-num {
  font-family: var(--font-serif);
  font-size: 2.5rem;
  font-weight: 900;
  line-height: 1;
  padding-top: 4px;
}
.flow-arrow {
  text-align: center;
  font-size: 1.4rem;
  color: var(--ink-muted);
  margin: 10px 0;
}
.result-section {
  margin-top: 28px;
  padding-top: 28px;
  border-top: 1px solid var(--divider);
}

/* ─── Taxonomy ───────────────────────────────────────── */
.taxonomy-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 28px;
  margin-top: 28px;
}
.taxonomy-item {
  padding-top: 16px;
  border-top: 2px solid var(--accent-a);
}

/* ─── Prose ──────────────────────────────────────────── */
.prose { font-size: .9rem; margin-bottom: 14px; }

/* ─── Steps ──────────────────────────────────────────── */
.steps { list-style: none; padding: 0; margin: 14px 0; }
.steps li { display: flex; gap: 10px; margin-bottom: 8px; font-size: .875rem; }
.step-num {
  font-family: var(--font-mono);
  font-size: .72rem;
  font-weight: 700;
  color: var(--ink-muted);
  min-width: 22px;
  padding-top: 2px;
}

/* ─── Pull quote ─────────────────────────────────────── */
.pull-quote {
  font-style: italic;
  font-size: 1.05rem;
  margin: 16px 0;
  color: var(--ink);
}

/* ─── Callouts ───────────────────────────────────────── */
.callout { border-radius: 4px; padding: 12px 16px; margin: 16px 0; }
.callout-warn {
  background: var(--callout-warn-bg);
  border-left: 3px solid var(--callout-warn-border);
}
.callout-note {
  background: var(--callout-note-bg);
  border-left: 3px solid var(--callout-note-border);
}
.callout-title {
  font-size: .62rem;
  font-weight: 700;
  letter-spacing: .09em;
  text-transform: uppercase;
  margin-bottom: 6px;
}
.callout-warn .callout-title { color: var(--accent-b); }
.callout-note .callout-title { color: var(--accent-a); }
.callout p { font-style: italic; font-size: .875rem; margin: 0; }

/* ─── Diagram chips ──────────────────────────────────── */
.diagram-label {
  font-size: .62rem;
  font-weight: 600;
  letter-spacing: .08em;
  text-transform: uppercase;
  color: var(--ink-muted);
  margin: 12px 0 6px;
}
.chip-row { display: flex; align-items: center; gap: 4px; flex-wrap: wrap; margin-bottom: 8px; }
.chip {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  height: 24px;
  padding: 0.2em;
  border-radius: 2px;
  font-family: var(--font-mono);
  font-size: .6rem;
  font-weight: 700;
  color: #fff;
}
.chip-empty {
  background: transparent !important;
  border: 1px dashed var(--divider);
  color: var(--ink-muted);
}
.chip-result { height: 28px; }
.arrow { color: var(--ink-muted); font-size: .85rem; }

/* ─── Comparison table ───────────────────────────────── */
.table-section { margin-top: 36px; }
.table-meta {
  font-size: .62rem;
  font-weight: 600;
  letter-spacing: .08em;
  text-transform: uppercase;
  color: var(--ink-muted);
  margin-bottom: 10px;
}
.comparison-table { width: 100%; border-collapse: collapse; font-size: .85rem; }
.comparison-table th {
  padding: 8px 12px;
  font-size: .75rem;
  font-weight: 700;
  text-align: left;
  background: var(--code-surface);
}
.comparison-table td { padding: 8px 12px; border-top: 1px solid var(--divider); }
.row-label {
  font-size: .62rem;
  font-weight: 700;
  letter-spacing: .07em;
  text-transform: uppercase;
  color: var(--ink-muted);
}
.comparison-table tr:nth-child(even) td {
  background: color-mix(in srgb, var(--surface) 80%, var(--divider));
}
.shared-note {
  font-size: .8rem;
  font-style: italic;
  color: var(--ink-muted);
  border-top: 1px solid var(--divider);
}

/* ─── Stat row ───────────────────────────────────────── */
.stat-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 40px;
  padding-top: 28px;
  border-top: 1px solid var(--divider);
}
.stat-number {
  font-family: var(--font-serif);
  font-size: 3.5rem;
  font-weight: 900;
  line-height: 1;
  letter-spacing: -0.03em;
}
.stat-unit { font-size: 2.5rem; }
.stat-label {
  font-size: .72rem;
  color: var(--ink-muted);
  font-style: italic;
  margin-top: 4px;
  max-width: 160px;
}
.stat-center { text-align: center; font-size: .9rem; line-height: 1.5; }
```