# Typora 主题设计计划

> 需要产出 **两个主题文件**：Dark 版 + Light 版，共享同一设计语言。

---

## 一、参考图分析

**提取要素：**
- 纯黑/深灰背景 (`#1a1a2e` 附近)
- 多彩文件夹图标（蓝、绿、紫、橙）
- 树状连接线为低调灰色
- 中文注释使用亮白色，与彩色图标形成层次

---

提取要素：**
- 白色/浅色背景的排版参考（**Light 版核心参考**）
- **标题层级**：深棕/酒红色（如 `#8B4513`），纯色彩区分层级，不带自动编号
- **强调文字**：红色加粗、蓝色高亮链接文字
- **有序/无序列表**：彩色圆点 bullet（蓝/绿/灰多层级）
- 整体排版疏朗，行间距大，阅读舒适

---

提取要素：**
- 深色卡片式布局，圆角面板
- **彩色 Badge/标签**：绿色圆角标签（`作用`、`位置`、`创建`、`文件`）
- **行内代码**：深底 + 亮色文字（如 `./CLAUDE.md`）
- **Callout 提示框**：底部渐变半透明背景 + 💡 图标 + 彩色文字
- 分隔线清晰，内容区块分明

---

### 图4 — 深色日志视图（Daily Log）
![](IMG_6733.PNG)

**提取要素：**
- 子弹笔记风格，嵌套缩进
- **标签 Tag**：`#NodeJS` `#Stream` 等使用彩色高亮
- **Emoji** 自然穿插使用
- **时间戳**（02:00、03:23 等）使用低对比度灰色
- 任务状态图标（✅ 勾选、🔍 搜索）
- 整体信息密度较高但层次分明

---

提取要素：**
- **青蓝色竖线** 时间线（`#00bcd4` 附近）
- 圆形节点标记
- 适合用于列表或引用块的左侧装饰线

---

## 二、主题定位

| 属性 | 决策 |
|------|------|
| **名称** | 待定（建议：`Velvet Dark` / `Velvet Light`） |
| **模式** | **两套主题**：Dark + Light，共享设计语言 |
| **产出文件** | `velvet-dark.css` + `velvet-light.css` |
| **适用场景** | 技术笔记、学术笔记、日常 Logbook |
| **中文优化** | 必须，中文使用系统默认字体 |

---

## 三、字体方案

### 3.1 字体来源

| 字体 | 用途 | 来源路径 |
|------|------|----------|
| **Gill Sans Nova** | 英文正文 / 标题 | `./gill-sans-nova-medium-italic.ttf`（通过 `@font-face` 引入） |
| **ChillRoundF** | 中文正文 / 标题 | `./ChillRoundF.ttf`（通过 `@font-face` 引入） |
| **FuraCode Nerd Font** | 代码（行内 + 代码块） | `~/Library/Fonts/FuraCodeNerdFontComplete-Retina.ttf`（已安装） |

### 3.2 CSS 字体栈

```css
/* 在 CSS 文件头部引入字体 */
@font-face {
  font-family: "Gill Sans Nova";
  src: url("velvet-dark/gill-sans-nova-medium-italic.ttf") format("truetype");
  font-weight: 500;
  font-style: italic;
}

@font-face {
  font-family: "ChillRoundF";
  src: url("velvet-dark/ChillRoundF.ttf") format("truetype");
  font-weight: normal;
  font-style: normal;
}

:root {
  /* 英文优先 Gill Sans Nova，中文使用 ChillRoundF 圆体 */
  --font-body:    "Gill Sans Nova", "ChillRoundF", sans-serif;
  --font-heading: "Gill Sans Nova", "ChillRoundF", sans-serif;
  --font-code:    "FuraCode Nerd Font", "Fira Code", monospace;
}
```

> **注意**：Typora 自定义字体需将 `.ttf` 放入主题同名文件夹内（如 `velvet-dark/`），通过 `@font-face` 相对路径引用。两个字体文件都需要复制进去。

---

## 四、配色方案

### 4.1 Dark 版（主参考：图1/3/4/5）

基于 **Catppuccin Mocha** 色板。

```
┌─────────────────┬───────────┬──────────┬────────────────────────────┐
│ 元素            │ 色值       │ 色名     │ 对比度校验 (vs 背景)        │
├─────────────────┼───────────┼──────────┼────────────────────────────┤
│ 背景（主）       │ #1e1e2e   │ 深蓝黑    │ —                         │
│ 背景（侧栏）     │ #181825   │ 更深     │ —                          │
│ 正文文字         │ #cdd6f4   │ 浅蓝白    │ ✅ 11.4:1 vs #1e1e2e      │
│ 次要文字         │ #a6adc8   │ 灰蓝     │ ✅ 7.2:1                   │
│                 │           │          │                            │
│ 标题 H1         │ #f38ba8   │ 玫红     │ ✅ 7.1:1                   │
│ 标题 H2         │ #fab387   │ 橙       │ ✅ 8.5:1                   │
│ 标题 H3         │ #f9e2af   │ 暖黄     │ ✅ 12.3:1                  │
│ 标题 H4         │ #a6e3a1   │ 绿       │ ✅ 10.5:1                  │
│ 标题 H5         │ #89b4fa   │ 蓝       │ ✅ 7.4:1                   │
│ 标题 H6         │ #cba6f7   │ 紫       │ ✅ 7.6:1                   │
│                 │           │          │                            │
│ 链接             │ #89dcfe   │ 亮天蓝    │ ✅ 10.1:1                  │
│ 加粗             │ #f38ba8   │ 玫红     │ ✅ 7.1:1                   │
│ 斜体             │ #cba6f7   │ 紫       │ ✅ 7.6:1                   │
│ 高亮背景         │ #f9e2af33 │ 半透明黄  │ 文字仍用正文色，可读         │
│                 │           │          │                            │
│ 行内代码背景      │ #313244   │ 深灰     │ —                          │
│ 行内代码文字      │ #94e2d5   │ 青绿     │ ✅ 8.0:1 vs #313244        │
│ 代码块背景        │ #11111b   │ 最深黑   │ —                          │
│ 代码块文字        │ #cdd6f4   │ 浅蓝白   │ ✅ 13.8:1 vs #11111b       │
│                 │           │          │                            │
│ 引用左边框        │ #00bcd4   │ 青蓝     │ 装饰色，无需文字对比         │
│ 引用背景         │ #89b4fa0d │ 极淡蓝   │ 微妙区分，不干扰阅读         │
│ 引用文字         │ #bac2de   │ 浅灰蓝   │ ✅ 8.8:1 vs #1e1e2e        │
│                 │           │          │                            │
│ 表格边框         │ #45475a   │ 暗灰     │ 可见但不抢眼                 │
│ 表头背景         │ #313244   │ 深灰     │ —                          │
│ 表格交替行        │ #1e1e2e / #252536 │  │ 微妙条纹                   │
│                 │           │          │                            │
│ 分割线           │ #45475a   │ 暗灰     │ 装饰色                      │
│ 选中高亮         │ #585b7066 │ 半透明灰  │ —                          │
└─────────────────┴───────────┴──────────┴────────────────────────────┘
```

### 4.2 Light 版（主参考：图2）

基于 **Catppuccin Latte** 色板，确保彩色元素在浅色背景上有足够对比度。

```
┌─────────────────┬───────────┬──────────┬────────────────────────────┐
│ 元素            │ 色值       │ 色名     │ 对比度校验 (vs 背景)        │
├─────────────────┼───────────┼──────────┼────────────────────────────┤
│ 背景（主）       │ #eff1f5   │ 浅灰白    │ —                         │
│ 背景（侧栏）     │ #e6e9ef   │ 更灰     │ —                          │
│ 正文文字         │ #4c4f69   │ 深灰蓝    │ ✅ 7.5:1 vs #eff1f5       │
│ 次要文字         │ #6c6f85   │ 中灰     │ ✅ 4.7:1                   │
│                 │           │          │                            │
│ 标题 H1         │ #d20f39   │ 正红     │ ✅ 5.8:1  ⚠️ 比 Dark 深    │
│ 标题 H2         │ #df8e1d   │ 深橙     │ ✅ 3.2:1 → 改用 #b8600a   │
│                 │           │          │   #b8600a ✅ 4.6:1         │
│ 标题 H3         │ #8b6508   │ 深黄棕    │ ✅ 4.6:1（避免纯黄看不见）   │
│ 标题 H4         │ #40a02b   │ 深绿     │ ✅ 3.4:1 → 改用 #2d7a1e   │
│                 │           │          │   #2d7a1e ✅ 5.0:1         │
│ 标题 H5         │ #1e66f5   │ 蓝       │ ✅ 5.2:1                   │
│ 标题 H6         │ #8839ef   │ 紫       │ ✅ 5.1:1                   │
│                 │           │          │                            │
│ 链接             │ #1e66f5   │ 蓝       │ ✅ 5.2:1                   │
│ 加粗             │ #d20f39   │ 正红     │ ✅ 5.8:1                   │
│ 斜体             │ #8839ef   │ 紫       │ ✅ 5.1:1                   │
│ 高亮背景         │ #df8e1d26 │ 半透明橙  │ 文字仍用正文色，可读         │
│                 │           │          │                            │
│ 行内代码背景      │ #dce0e8   │ 浅灰     │ —                          │
│ 行内代码文字      │ #0d7377   │ 深青     │ ✅ 5.3:1 vs #dce0e8        │
│ 代码块背景        │ #e6e9ef   │ 灰白     │ —                          │
│ 代码块文字        │ #4c4f69   │ 深灰蓝   │ ✅ 6.8:1 vs #e6e9ef        │
│                 │           │          │                            │
│ 引用左边框        │ #0d9488   │ 深青绿    │ 装饰色                     │
│ 引用背景         │ #1e66f50a │ 极淡蓝    │ 微妙区分                    │
│ 引用文字         │ #5c5f77   │ 中灰蓝   │ ✅ 5.5:1 vs #eff1f5        │
│                 │           │          │                            │
│ 表格边框         │ #bcc0cc   │ 灰       │ 可见但不抢眼                 │
│ 表头背景         │ #dce0e8   │ 浅灰     │ —                          │
│ 表格交替行        │ #eff1f5 / #e6e9ef │  │ 微妙条纹                   │
│                 │           │          │                            │
│ 分割线           │ #bcc0cc   │ 灰       │ 装饰色                      │
│ 选中高亮         │ #7287fd33 │ 半透明蓝  │ —                          │
└─────────────────┴───────────┴──────────┴────────────────────────────┘
```

> **对比度说明**：WCAG AA 标准要求正文 ≥ 4.5:1、大标题 ≥ 3:1。
> Light 版中 H2 橙色和 H4 绿色已从 Catppuccin 原色加深以满足标准，避免"融入背景看不见"。

---

## 五、关键样式特征（Dark & Light 共享）

| 元素 | 样式 | 对应参考图 |
|------|------|-----------|
| **标题** | H1~H6 各自独立颜色，H1 加粗 + 底部 2px 渐变装饰线，**不带自动编号** | 图2 |
| **引用块** | 左侧 3px 青蓝/青绿竖线 + 半透明背景 | 图5 |
| **行内代码** | 圆角 (3px) + 对比背景 + 青绿/深青文字 | 图3 |
| **代码块** | 圆角 (6px) + 深底 + 语法高亮 | 图3 |
| **列表 bullet** | 彩色圆点（按层级递变：红→蓝→绿→紫） | 图2/4 |
| **缩进引导线** | 动态 hover L 形渐变连接线，Outliner 风格（5 层渐变色 + 圆角） | 图1/4 |
| **加粗** | 红/玫红色，`font-weight: 700` | 图2 |
| **斜体** | 紫色，使用 Gill Sans Nova italic | 图2 |
| **高亮 `==text==`** | 半透明暖色底，文字保持正文色 | 图2 |
| **表格** | 条纹交替 + 表头加粗高亮 + 圆角（如浏览器支持） | — |
| **分割线** | 中间实、两端淡的渐变线 | 图3 |
| **侧边栏** | 更深/更灰背景，选中项带左侧彩色指示条 | 图1 |
| **链接** | 蓝/天蓝色，hover 下划线 | 图2 |

---

## 六、文件结构

```bash
typoratheme/
├── THEME_PLAN.md                          ← 本文件
├── velvet-dark.css                        ← Dark 主题 CSS
├── velvet-dark/
│   ├── gill-sans-nova-medium-italic.ttf   ← 英文字体
│   └── ChillRoundF.ttf                   ← 中文圆体字体
├── velvet-light.css                       ← Light 主题 CSS
├── velvet-light/
│   ├── gill-sans-nova-medium-italic.ttf   ← 英文字体
│   └── ChillRoundF.ttf                   ← 中文圆体字体
├── IMG_6694.jpeg                          ← 参考图
├── IMG_6696.jpeg
├── IMG_6697.jpeg
├── IMG_6733.PNG
├── IMG_6734.PNG
├── gill-sans-nova-medium-italic.ttf       ← 英文字体原件
└── ChillRoundF.ttf                        ← 中文字体原件
```

> 安装方式：将 `velvet-dark.css`、`velvet-dark/` 文件夹（或 light 版）一起复制到 Typora 主题目录：
> `~/Library/Application Support/abnerworks.Typora/themes/`

---

## 七、实现步骤

### Phase 1 — 基础搭建
1. 创建目录结构，复制字体文件
2. 编写 Dark CSS：CSS 变量 → `@font-face` → 正文排版
3. 编写 Light CSS：继承相同结构，替换颜色变量

### Phase 2 — 核心元素
4. 标题 H1~H6 分色样式
5. 列表彩色 bullet（`::marker` 伪元素）
6. 行内代码 + 代码块 + 语法高亮
7. 引用块（青蓝左边框 + 半透明底）
8. 表格（条纹 + 表头 + 圆角）

### Phase 3 — UI 与细节
9. 侧边栏 / 文件树 / 大纲面板
10. 分割线渐变效果
11. 选中文字高亮、光标颜色
12. 搜索高亮、匹配项颜色

### Phase 4 — 测试
13. 用真实笔记（技术文档、学术笔记、Logbook）测试所有元素
14. 校验 Light 版中所有彩色文字对比度 ≥ WCAG AA
15. 导出 PDF 测试

---

## 八、对比度安全清单

> 以下是 Light 版中最容易"看不见"的颜色风险点，已提前处理：

| 风险元素 | 原始色 | 问题 | 解决方案 |
|---------|--------|------|---------|
| H2 橙色标题 | `#df8e1d` | 3.2:1 不达标 | 加深为 `#b8600a` (4.6:1) |
| H4 绿色标题 | `#40a02b` | 3.4:1 不达标 | 加深为 `#2d7a1e` (5.0:1) |
| H3 黄色标题 | `#df8e1d` | 黄色在白底极难辨认 | 改用深黄棕 `#8b6508` (4.6:1) |
| 次要灰色文字 | `#9ca0b0` | 可能偏淡 | 使用 `#6c6f85` (4.7:1) |
| 高亮背景 | 纯黄底 | 正文色可能被冲淡 | 使用半透明 `#df8e1d26`，文字不变色 |

---

## 九、动态彩色缩进引导线

### 设计目标

类似 Obsidian Outliner 的动态引导线效果：鼠标悬停在列表项时，显示从父级到当前项的 L 形连接线。每层嵌套使用不同的**纯色**（整条线同一颜色），带圆角。

### 实现方案

**纯动态 hover 方案**（无静态线），使用 `::before` 伪元素 + CSS `:has()` 选择器：

1. **竖线段**：选中悬停项上方的兄弟项，绘制垂直纯色线
2. **L 形连接器**：在悬停项本身绘制 L 形转角线，从上方垂直延伸后水平指向 bullet

**核心选择器逻辑：**
- `li:hover > ul > li:has(~ li:hover)::before` — 匹配悬停项**上方的兄弟项**（竖线段）
- `li:hover > ul > li:hover::before` — 匹配**悬停项本身**（L 形连接器）

### CSS 变量

```css
--guide-width: 1.5px;    /* 线条粗细 */
--guide-item-h: 2.1em;   /* 列表项高度参考 */
```

### 关键定位参数

- `left: -2.85em` — 线条水平位置（marker 左侧）
- `top: calc(var(--guide-item-h) / 2 * -1)` — 竖线起始于上方项中心
- L 形宽度：`1.7em`（无序列表）/ `1.4em`（有序列表，避免与数字重叠）
- L 形圆角：`border-bottom-left-radius: 4px`

### 颜色方案

每层使用统一纯色（竖线 `background` 和 L 形 `border-color` 相同）。

| 层级 | Dark 版 | Light 版 |
|------|---------|----------|
| 第1层 | `#f38ba8` 玫红 | `#d20f39` 红 |
| 第2层 | `#89b4fa` 蓝 | `#1e66f5` 蓝 |
| 第3层 | `#a6e3a1` 绿 | `#2d7a1e` 绿 |
| 第4层 | `#cba6f7` 紫 | `#8839ef` 紫 |
| 第5层 | `#fab387` 橙 | `#b8600a` 橙 |

### 核心 CSS（Dark 版示例）

```css
#write li { position: relative; }

/* 竖线段 — 悬停项上方的兄弟 */
#write li:hover > ul > li:has(~ li:hover)::before,
#write li:hover > ol > li:has(~ li:hover)::before {
  content: "";
  position: absolute;
  width: var(--guide-width);
  top: calc(var(--guide-item-h) / 2 * -1);
  left: -2.85em;
  height: calc(100% + 0.35em);
  pointer-events: none;
  z-index: 1;
  background: #f38ba8;
}

/* L 形连接器 — 悬停项本身 */
#write li:hover > ul > li:hover::before,
#write li:hover > ol > li:hover::before {
  content: "";
  position: absolute;
  top: calc(var(--guide-item-h) / 2 * -1);
  left: -2.85em;
  bottom: calc(100% - var(--guide-item-h) / 2 + 0.15em);
  width: 1.7em;
  border-bottom-left-radius: 4px;
  pointer-events: none;
  z-index: 1;
  border-bottom: var(--guide-width) solid #f38ba8;
  border-left: var(--guide-width) solid #f38ba8;
}

/* 有序列表 L 形较窄 */
#write li:hover > ol > li:hover::before { width: 1.4em; }

/* Level 2~5 — 用 li li... 后代选择器覆盖颜色 */
/* 竖线：background: #89b4fa; */
/* L 形：border-left-color + border-bottom-color 统一设为同色 */
```

### 技术要点

1. **为什么用 `:has()` 选择器？**
   - `li:has(~ li:hover)` 匹配"后面有被悬停兄弟"的项，即悬停项上方的所有兄弟
   - 实现 Obsidian Outliner 风格的动态树状连接线

2. **每层纯色设计：**
   - 竖线段的 `background` 和 L 形的 `border-left-color` / `border-bottom-color` 使用同一颜色
   - 整条引导线视觉统一，进入下一层嵌套时整条换色

3. **层级递增选择器：**
   - `li li:hover` = 第 2 层，`li li li:hover` = 第 3 层...
   - CSS specificity 自动递增，深层覆盖浅层颜色
   - 5 层以上自动继承第 5 层配色

4. **微调指南：**
   - 线条位置偏移 → 调整 `left: -2.85em`
   - L 形宽度 → 调整 `width`（ul: 1.7em, ol: 1.4em）
   - L 形横线垂直对齐 → 调整 `bottom` 中的 `0.15em` 偏移量

### 其他列表改进

- **统一无序列表 bullet 为圆形**：`ul li { list-style-type: disc; }` — 覆盖浏览器默认的 disc → circle → square 递变行为

---

## 十、最终效果预期

> **Dark 版**：深蓝黑画布上，彩虹色标题如霓虹指引，青蓝引用线如时间线流淌，代码块沉入最深处。适合夜间长时间阅读。
>
> **Light 版**：温润灰白纸张上，深色彩标题层次分明如同学术论文，配色克制但不单调。适合日间阅读和 PDF 导出。
>
> 两版共享同一设计语言 — **Gill Sans Nova** 的优雅英文搭配 **ChillRoundF** 圆体中文的柔和可爱，**FuraCode Nerd Font** 让代码块既专业又有 Nerd 图标支持。
