# Layout Primitives

High-level containers. They are **greedy** — expand to fill available space.

---

## `<Dashboard>`

Root wrapper. Always required.

| Prop       | Type                      | Notes                 |
| ---------- | ------------------------- | --------------------- |
| `title`    | string                    | Main document heading |
| `subtitle` | string                    | Secondary descriptor  |
| `layout`   | `stacked` \| `asymmetric` | Default: `stacked`    |

---

## `<Grid>`

Multi-column card layout.

| Prop       | Type                                  | Notes                            |
| ---------- | ------------------------------------- | -------------------------------- |
| `columns`  | 1–4                                   | Number of columns                |
| `gap`      | `tight` \| `standard` \| `expressive` | Default: `standard`              |
| `variant`  | SemanticVariant                       | See variants.md                  |
| `fillMode` | `card` \| `subtle-tint` \| `none`     | Default: `none`                  |
| `glow`     | boolean                               | Soft radial glow behind the grid |

---

## `<TwoColumn>`

Split layout — main content + sidebar lane.

| Prop            | Type                              | Notes                               |
| --------------- | --------------------------------- | ----------------------------------- |
| `proportion`    | `50/50` \| `70/30`                | Default: `70/30`                    |
| `variant`       | SemanticVariant                   | See variants.md                     |
| `accentBorders` | boolean                           | Vertical accent line on each column |
| `fillMode`      | `card` \| `subtle-tint` \| `none` | Default: `none`                     |
| `glow`          | boolean                           | —                                   |

Children: pass exactly two child elements — first is the wide column, second is the narrow.

---

## `<StepSection>`

Numbered narrative section. Use for sequenced steps or major document phases.

| Prop         | Type                              | Notes                     |
| ------------ | --------------------------------- | ------------------------- |
| `stepNumber` | number                            | Renders as ❶ ❷ ❸ …        |
| `title`      | string                            | Section heading           |
| `tagline`    | string                            | Optional muted subheading |
| `variant`    | SemanticVariant                   | See variants.md           |
| `fillMode`   | `card` \| `subtle-tint` \| `none` | Default: `none`           |
| `glow`       | boolean                           | —                         |

---

## `<InteractiveTabs>`

Client-side tab panel switcher.

| Prop     | Type      | Notes                                           |
| -------- | --------- | ----------------------------------------------- |
| `labels` | string[]  | Tab label array (e.g. `['Overview', 'Detail']`) |
| children | ReactNode | One child element per label, in order           |
