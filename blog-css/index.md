# CSS 强化


<!--more-->

## CSS 

### 与 HTML 的关系

- 内容与结构的分离
- 在 HTML 上嵌入层叠样式表
  - 外部引用 .css
  - 内部/局部使用`<style>`, `<p style="">`

### 基本语法

- 属性内分隔符`,`
- 属性间分隔符`;`
- 允许叠加属性符 `ex: top right`

- `background`**背景**

  `-color` 背景色

  `-image: url(pic.file)` 背景图片

  `-repeat: repeat/no-repeat` 重复性

  `-position: center/right/top/100px 100px` 位置

  `-attchment: scroll/fixed` 固定性

- **文本段落**

  - 格式

    `text-indent: -2em/10%/2in/2cm` 首行缩进

    `padding: 2em ` 悬挂缩进 即非首行的缩进

    `line-height: normal/1.5` 行距 倍数

    `text-align: left/right/center/justify` 对齐 (justify: 两端对齐)

    `word-spacing: 10px` 空格大小

    `letter-spacing: 10px` 字符间距

    `text-transform: uppercase/lowcase/capitalize` 变形: 全大写/小写/首字母大写

    `text-decoration: underline/overline/linethrough ` 文本装饰

    `white-space: normal/pre/wrap/no-wrap/pre-line` 空白符样式

    `direction: ltr/rtl` 方向

  - **字体**

    `font-family: serif/sans-serif/nomospace`

    `font-style: italic/obique` 斜体/计算斜体

    `font-variant: small-caps` 大写字母缩小

    `font-weight: 400/bold` 字重

    `font-size: 0.5em/10px`

    `text-shadow: 3px 5px 5px rgba(r,g,b,a)` 阴影: x, y, z 轴延伸值

    `outline-color: redl; outline-style: solid/double; outline-width: 1` 轮廓

  - **列表**

    `<ul style="list-style[keyword]: [keyword]">`

    ` -type: disc/circle/square`

    `-position: `

  - 表格

  - 

- 颜色

  `transparent` 关键字 (透明)

  `#ffffff` 十六进制

  `rgb(255,255,0)` 十进制 (0~255)

  `rgba(r,g,b,a)` a=alpha 透明度 (0~1)

## HTML-MarkDown 对照表

| 描述     | markdown                    | HTML TAG   |
| -------- | --------------------------- | ---------- |
| 标题     | `# 一级标题` `## 二级标题`… | h1,h2…h6   |
| 粗体     | `**粗体**`                  | b , strong |
| 斜体     | `*斜体*`                    | em, i      |
| 分割线   | `---`                       | hr         |
| 无序列表 | `* 1` `- 1` `+ 1`           | ul         |
| 有序列表 | `1.`                        | ol         |
| 引用     | `>`                         | blockquote |
| 超链接   | `[url](url)`                | a          |
| 图片     | `![img](imgUrl)`            | img        |
| 表格     | 见下                        | table      |
| 代码段   | 见下                        | code       |
| 段落     | 无特殊表示                  | p          |
