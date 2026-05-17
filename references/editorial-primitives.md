# Editorial Primitives

Callouts, takeaways, and inline emphasis components.

---

## `<EditorialCallout>`

Prominent summary container. Use for thesis statements, key insights, risks, and conclusions.

| Prop        | Type            | Notes                                             |
| ----------- | --------------- | ------------------------------------------------- |
| `variant`   | SemanticVariant | Sets the entire tone. See variants.md             |
| `badgeText` | string          | Uppercase bold label (e.g. `"THE BET"`, `"RISK"`) |
| `text`      | string          | Main paragraph content                            |

---

## `<HighlightBox>`

General highlight block. Wraps any child content in a bordered surface panel.

No required props — wrap any MDX content inside it.

---

## `<Marker>` (inline)

Highlight a key phrase inside prose. Renders inline within `<p>` text.

| Prop         | Type               | Notes                        |
| ------------ | ------------------ | ---------------------------- |
| `color`      | SemanticVariant    | Accent color for the text    |
| `importance` | `bold` \| `subtle` | Font weight. Default: `bold` |

**Example:**

```mdx
The system extracts <Marker color="success">high-value KV tokens</Marker> first.
```

---

## `<Badge>` (inline)

Status label attached inline next to headings or metrics.

| Prop      | Type            | Notes                                               |
| --------- | --------------- | --------------------------------------------------- |
| `text`    | string          | Label content (e.g. `"SCALABLE"`, `"EXPERIMENTAL"`) |
| `variant` | SemanticVariant | Color theme                                         |

**Example:**

```mdx
### Decode Phase <Badge text="BOTTLENECK" variant="critical" />
```
