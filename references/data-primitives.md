# Data Primitives

Self-contained metric and data visualization components. They are **intrinsic** — they never stretch to fill parent layouts.
Strict enum values provided are to be followed exactly.

---

## `<MetricCard>`

Single KPI or status signal.

| Prop          | Type                                  | Notes                                                                            |
| ------------- | ------------------------------------- | -------------------------------------------------------------------------------- |
| `label`       | string                                | Short descriptor                                                                 |
| `value`       | string \| number                      | The primary display value                                                        |
| `trend`       | `positive` \| `negative` \| `neutral` | Default: `neutral`. MUST be exactly one of: `positive`, `negative`, or `neutral` |
| `description` | string                                | Muted supporting context                                                         |

---

## `<HeroStat>`

Large editorial number callout — use as a section takeaway.

| Prop        | Type                          | Notes                      |
| ----------- | ----------------------------- | -------------------------- |
| `stat`      | string \| number              | e.g. `4x`, `75%`, `2.3B`   |
| `label`     | string                        | Description below the stat |
| `alignment` | `left` \| `center` \| `right` | Default: `left`            |
| `variant`   | SemanticVariant               | See variants.md            |

---

## `<DataArray>`

Token sequences, byte maps, or memory slot visualizers.

| Prop               | Type            | Notes                                                |
| ------------------ | --------------- | ---------------------------------------------------- |
| `blocks`           | string[]        | Each element is one cell (e.g. `['t0','t1','t2']`)   |
| `highlightIndices` | number[]        | Indices to accent (0-based)                          |
| `arrowTarget`      | string          | Optional label after a `→` arrow (e.g. `"KV Cache"`) |
| `variant`          | SemanticVariant | Applied to highlighted cells                         |

---

## `<ValueStack>`

Layered blocks with proportional heights — use for ability stacks, allocation breakdowns.

| Prop      | Type            | Notes                                 |
| --------- | --------------- | ------------------------------------- |
| `items`   | Item[]          | Array of `{ label, weight, status? }` |
| `variant` | SemanticVariant | Default color for unlabeled items     |

`Item.weight` is relative — the compiler sizes each layer proportionally.
`Item.status` accepts any SemanticVariant to color that specific layer.

---

## `<DataChart>`

Trend lines, bar distributions, area fills using Recharts.

| Prop      | Type                                | Notes                        |
| --------- | ----------------------------------- | ---------------------------- |
| `type`    | `line` \| `column` \| `area`        | Chart style                  |
| `data`    | `{ name: string, value: number }[]` | Data array                   |
| `height`  | number                              | Pixel height. Default: `300` |
| `animate` | boolean                             | Default: `true`              |
