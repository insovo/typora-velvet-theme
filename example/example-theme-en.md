# Velvet Theme Showcase (English)

> Use this file in both `Velvet Dark` and `Velvet Light` for a side-by-side feel test.

## Why Velvet

- Fast structure scanning from clear heading hierarchy
- Consistent card UI across tables, quotes, and code blocks
- Comfortable long-form rhythm (spacing, line-height, contrast)
- Strong technical writing readability (inline + fenced code)
- macOS-like sidebar behavior for file navigation

## 1. Heading and Text Hierarchy

This paragraph is intentionally neutral so you can inspect body readability.
Check **bold**, *italic*, `inline code`, and ==highlight== behavior.

### 1.1 Practical Benefit

In long notes, clear level contrast reduces search time and cognitive load.

#### 1.1.1 Typical Use Cases

- engineering docs
- study notes
- design decisions

## 2. Blockquotes (Card Style)

> Blockquotes are ideal for conclusions, warnings, and review notes.
>
> Velvet turns them into subtle cards instead of plain left borders.

> A second quote for spacing and rhythm check.

## 3. Nested Lists

- Level 1
  - Level 2
    - Level 3
      - Level 4
        - Level 5

1. Ordered 1
   1. Ordered 2
      1. Ordered 3
         1. Ordered 4
            1. Ordered 5
               1. Ordered 6
                  1. Ordered 7

## 4. Code Rendering

Inline commands: `git diff`, `pnpm lint`, `npm run build`.

> Language labels appear as plain text in the top-right corner of each fenced code block.

```bash
# inspect key theme variables
rg -n -e "--h[1-6]" -e "--sidebar" -e "--table-radius" -e "--font-" velvet-dark.css velvet-light.css
```

```yaml
theme:
  dark: velvet-dark.css
  light: velvet-light.css
advantages:
  - clear hierarchy
  - card-like layout
  - macOS-like sidebar
```

```js
const summary = (name) =>
  `${name}: readable hierarchy, stable rhythm, and focused technical writing.`;

console.log(summary("Velvet"));
```

## 5. Tables (Rounded Card UI)

| Dimension | Velvet Dark | Velvet Light |
|---|---|---|
| Reading mood | immersive | airy |
| Heading contrast | stronger | calmer |
| Quote/Code cards | denser focus | lighter surface |
| Export usage | dark preview | print-like output |

## 6. Task List

- [x] Checked task gets strikethrough
- [x] Inline code remains readable with mixed language
- [ ] Highlight is visible in edit mode
- [ ] Validate with one real long-form document

## 7. Quick Input (Espanso)

Pair with [Espanso](https://espanso.org/) for quick timestamp insertion in Typora:

| Trigger | Expands to | Example |
|---|---|---|
| `:now` | date + time | `2026-03-06 14:30:25` |
| `:date` | date only | `2026-03-06` |
| `:time` | time only | `14:30:25` |

---

When switching themes, focus on scan speed, fatigue level, and code readability.
