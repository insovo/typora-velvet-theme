# Velvet Theme Showcase (English Sample)

> Open this file in both `Velvet Dark` and `Velvet Light` to compare how the same content behaves across two visual modes.

## 1. Heading Hierarchy and Emphasis

This paragraph is intentionally plain to reveal body typography, spacing rhythm, and readability.  
Check **bold text**, *italic text*, and `inline code` contrast in both themes.  
Also test `==highlighted text==` to see the warm translucent marker style.

### 1.1 Why This Theme Stands Out

- Color-coded heading levels make large notes scannable
- Inline code is clearly separated from prose
- Blockquotes create visual anchors for insights and summaries

#### 1.1.1 Links and Notes

Useful links:
- [Typora Official Site](https://typora.io/)
- [Markdown Guide](https://www.markdownguide.org/)

> Primary quote block: ideal for decisions, warnings, and key conclusions.  
> You can place `commands`, **keywords**, and [links](https://example.com/) inside.

> Secondary quote block for spacing and border rhythm checks.

## 2. Deep Nested Lists (Showcase for Indent Guide Lines)

- Level 1: project direction
  - Level 2: product goals
    - Level 3: reading flow
      - Level 4: visual hierarchy
        - Level 5: deep nesting clarity check
  - Level 2: implementation quality
    - Level 3: long-form readability
      - Level 4: annotation visibility
        - Level 5: fast structural navigation

1. Ordered level 1
   1. Ordered level 2
      1. Ordered level 3
         1. Ordered level 4
            1. Ordered level 5

## 3. Code Rendering (Inline + Fenced Blocks)

Inline commands: `npm run test`, `git diff`, `pnpm build`.

```bash
# Shell: verify theme font variables
rg -n "font-body|font-heading|font-code" velvet-dark.css velvet-light.css
```

```javascript
const summary = (theme) =>
  `${theme}: vibrant headings, clear structure, and focused code blocks.`;

console.log(summary("Velvet Dark"));
```

```yaml
theme:
  dark: velvet-dark.css
  light: velvet-light.css
fonts:
  body: ["Gill Sans Nova", "寒蝉全圆体"]
  code: ["FuraCode Nerd Font"]
```

```sql
SELECT section, impact
FROM theme_features
WHERE visibility = 'high'
ORDER BY impact DESC;
```

## 4. Table Density and Readability

| Dimension | Velvet Dark | Velvet Light |
|---|---|---|
| Overall mood | immersive, low-light friendly | clean, daylight friendly |
| Heading contrast | vivid and dramatic | crisp and restrained |
| Quote styling | stronger cyan accent | fresher teal accent |
| Code blocks | deep focus surface | lighter, print-friendly surface |
| Best for | night writing / deep review | daytime notes / PDF export |

## 5. Checklist and Micro Elements

- [x] Heading color hierarchy checked
- [x] Inline code and fenced block readability checked
- [x] Quote border and background checked
- [x] Nested-list guide lines checked
- [ ] Run one real long-note reading pass

---

Use this divider to evaluate horizontal rhythm and spacing transitions.  
When switching themes, focus on scan speed, fatigue level, and code readability over long sessions.
