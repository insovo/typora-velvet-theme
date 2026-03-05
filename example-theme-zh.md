# Velvet 主题展示（中文示例）

> 推荐分别在 `Velvet Dark` 和 `Velvet Light` 下打开此文件，对比同一内容在两套配色中的阅读体验。

## 1. 标题层级与文本强调

这段正文用于观察默认段落字体、行高与中英文混排效果。  
你可以注意 **加粗文本**、*斜体文本*、以及 `行内代码` 的对比度和可读性。  
还可以试试 `==高亮文本==`，看暖色半透明底在两套主题里的视觉表现。

### 1.1 快速亮点

- 彩色标题分层明显，长文结构更容易扫描
- 行内代码有独立底色与字体，适合术语与参数标注
- 引用块有竖向强调线，适合提示、定义与结论

#### 1.1.1 链接与引用

参考链接：
- [Typora 官方网站](https://typora.io/)
- [Markdown Guide](https://www.markdownguide.org/)

> 这是一级引用块：适合写提示、摘要或复盘结论。  
> 你也可以在引用里放 `命令`、**重点**、以及 [链接](https://example.com/)。

> 这是另一个引用块，用来观察块间距和边框节奏。

## 2. 多层列表（重点展示缩进引导线）

- 第一层：项目总览
  - 第二层：功能特性
    - 第三层：视觉层级
      - 第四层：颜色递进
        - 第五层：用于检验深层嵌套是否仍清晰
  - 第二层：排版体验
    - 第三层：长段落可读性
      - 第四层：标注信息可见性
        - 第五层：扫描速度与注意力引导

1. 第一层有序项
   1. 第二层有序项
      1. 第三层有序项
         1. 第四层有序项
            1. 第五层有序项

## 3. 代码展示（行内 + 代码块）

示例命令：`npm run build`、`git status`、`pnpm lint`。

```bash
# Shell: 快速检查主题文件
ls -la
rg -n "font-family|--font-body|--font-code" velvet-dark.css velvet-light.css
```

```json
{
  "theme": "velvet-dark",
  "font_body": ["Gill Sans Nova", "寒蝉全圆体"],
  "font_code": ["FuraCode Nerd Font"],
  "notes": "use system-installed fonts only"
}
```

```css
:root {
  --font-body: "Gill Sans Nova", "寒蝉全圆体", sans-serif;
  --font-code: "FuraCode Nerd Font", monospace;
}
```

```python
def summarize(theme_name: str) -> str:
    return f"{theme_name}: colorful headings, clear hierarchy, calm reading rhythm."

print(summarize("Velvet Light"))
```

## 4. 表格与信息密度

| 维度 | Velvet Dark | Velvet Light |
|---|---|---|
| 整体气质 | 沉稳、夜读友好 | 明亮、日读友好 |
| 标题层级 | 强对比霓虹感 | 深色层次更克制 |
| 引用块 | 青蓝强调线更醒目 | 青绿强调线更清爽 |
| 代码区块 | 深底聚焦强 | 浅底阅读轻松 |
| 适用场景 | 夜间笔记 / 深度写作 | 日间整理 / 导出 PDF |

## 5. 任务清单与细节元素

- [x] 验证标题颜色层级
- [x] 验证代码块与行内代码
- [x] 验证引用块边线与背景
- [x] 验证列表多层缩进与引导线
- [ ] 用真实文档再做一次长文阅读测试

---

这条分割线用于观察主题的横向视觉节奏。  
如果你在两套主题间切换，建议重点看：标题辨识速度、代码可读性、以及长列表的导航感。
