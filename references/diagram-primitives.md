# Diagram Primitives

Structural and flow diagram components.

---

## `<ProcessPipeline>`

Horizontal ordered chain of steps linked by arrows. Use for linear pipelines, build sequences, inference stages.

| Prop      | Type            | Notes                                  |
| --------- | --------------- | -------------------------------------- |
| `steps`   | Step[]          | Ordered array of `{ label, subtext? }` |
| `variant` | SemanticVariant | See variants.md. Default: `info`       |

---

## `<SystemLoop>`

Multi-node cyclic system with directed arrows. Use for agent loops, feedback cycles, recurring workflows.

| Prop          | Type            | Notes                                        |
| ------------- | --------------- | -------------------------------------------- |
| `nodes`       | Node[]          | Array of `{ id, title, description? }`       |
| `connections` | Conn[]          | Array of `{ from, to }` referencing node IDs |
| `variant`     | SemanticVariant | See variants.md. Default: `system`           |

Node `id` values must be unique strings. `connections` reference them by ID. Arrows are rendered as animated SVG paths.

**Example:**

```mdx
<SystemLoop
  nodes={[
    { id: "proposer", title: "Proposer", description: "Generates candidate" },
    { id: "judge", title: "Judge", description: "Evaluates output" },
  ]}
  connections={[
    { from: "proposer", to: "judge" },
    { from: "judge", to: "proposer" },
  ]}
  variant="system"
/>
```

---

## `<ArchitectureTree>`

File tree or dependency hierarchy. Use for project structures, module trees, data flow hierarchies.

| Prop       | Type   | Notes                                       |
| ---------- | ------ | ------------------------------------------- |
| `rootName` | string | Root node label                             |
| `nodes`    | Node[] | Array of `{ name, type, desc?, children? }` |

Node `type` accepts: `file`, `folder`, `link`.
`children` is a nested array of the same Node shape — supports arbitrary depth.
