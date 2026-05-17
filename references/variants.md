# Semantic Variants

All components that accept a `variant` prop use this shared color palette. Pick based on the **semantic meaning** of the content — the compiler applies the correct colors automatically.

| Variant    | Meaning       | Use for                                           |
| ---------- | ------------- | ------------------------------------------------- |
| `default`  | Neutral       | General content, no specific status               |
| `info`     | Analytical    | Data streams, technical breakdowns, metrics       |
| `system`   | Architectural | Processes, pipelines, agent loops, infra          |
| `success`  | Positive      | Gains, optimizations, additions, results          |
| `critical` | Risk          | Failures, removals, breaking conditions, warnings |
| `insight`  | Editorial     | Takes, conclusions, thesis statements, opinions   |

---

## `fillMode`

Controls background rendering for layout containers (`Grid`, `TwoColumn`, `StepSection`):

| Value         | Appearance                                         |
| ------------- | -------------------------------------------------- |
| `none`        | Transparent — no background                        |
| `subtle-tint` | Soft edge-to-edge tinted wash matching the variant |
| `card`        | Solid floating surface panel with border           |

---

## `glow`

Boolean prop available on layout containers. When `true`, applies a subtle radial background glow using the variant accent color. Use sparingly — one or two per document maximum.
