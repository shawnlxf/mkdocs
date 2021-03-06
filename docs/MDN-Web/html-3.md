# 章节标签 / 文本标签

## 1 章节标签

> 都是块级元素, block-level elements

!!! note "1. h1–h6: 标题 (section heading)"

??? note "2. section: 部分"

    `<section>` 元素表示一个包含在 HTML 文档中的独立部分，它没有更具体的语义元素来表示。
    
    通常，但并不总是如此，各节都有标题。

    例如，导航菜单应该包含 (wrapped) 在 `<nav>` 元素中，但 搜索结果列表 和 地图显示 及其控件 没有特定的元素，可以放在 `<section>` 里。

    * 一个经验法是，`<section>` 应该出现在文档大纲中。

??? note "3. article: 文章"

    HTML `<article>` 元素表示一个文档，页面，应用程序或网站里的自包含文章，意图可以 独立地分发 或 可以重复使用（例如，在报刊辛迪加）。
    
    例子包括：论坛帖子，杂志 或 报纸文章 或 博客条目。

    * 每个 `<article>` 应该被标识，通常通过包含一个标题 (`<h1>`-`<h6>`) 作为其子元素
    * 当 `<article>` 元素嵌套时，内部元素代表与外部元素相关的文章。例如，博客帖子的评论可以是嵌套在表示博客帖子的 `<article>` 中的 `<article>` 元素。
    * `<article>` 元素的作者信息可以通过 `<address>` 元素提供，但不适用于嵌套的 `<article>` 元素。
    * 可以使用 `<time>` 元素的 datetime 属性来描述 `<article>` 元素的发布日期和时间。


??? note "4. header: 页眉"


    `<header>` 元素表示介绍性内容，通常是一组介绍性的或是导航的帮助内容。
    
    它可能包含一些标题元素，但也可能包含其他元素，比如 Logo、search form、作者名等等。

    * `<header>` 元素通常用于包含周围章节的标题（h1-h6 元素），但这不是必需的。

??? note "5. footer: 页脚"

    `<footer>` 元素表示一个它最近的 sectioning content 或 sectioning root 元素的页脚。

    一个页脚通常包含该章节的作者、版权数据或者与文档相关的链接的信息。

    * `<address>` 元素中关于作者的信息，可以包含在 `<footer>` 元素内


??? note "6. main: 主要内容"

    文档的主要内容 或 应用的中心功能

    一个文档最多只能包含一个没有指定 hidden 属性的 `<main>` 元素。

    存在于任意一系列文档 中的重复内容，比如侧边栏、导航栏链接、版权信息、网站 Logo 和 search forms（除非 search form 为页面的主要功能），都不应被包括在内。

    `<main>` 对文档的大纲没有贡献；也就是说，与 `<body>`, `<h2>` 等元素不同，`<main>` 不会影响 DOM 的页面结构概念。它只提供信息。

??? note "7. aside: 旁支内容"

    与文档主要内容间接相关。
    
    asides 经常呈现为 sidebars (侧边栏) 或 call-out boxes (标注框).


## 2 内容标签

### 2.1 block

??? note "1. ol: 有序列表, ul: 无序列表"

    ordered list, unordered list

    ol 属性：

        * reversed: 布尔属性
        * start: 总是阿拉伯数字
        * type: 设置编号类型

            > 除非列表编号的类型很重要（例如法律或技术文档，其中以编号/字母引用项目），否则请使用CSS `list-style-type` 属性。


??? note "2. li"

    list item

    它必须包含在一个父元素里：`<ol>`，`<ul>`，或者 `<menu>`。

    属性：

        * value: 指示 `<ol>` 中的 li 的当前序号。只能用数字。之后继续编号
        * CSS `list-style-type` property

??? note "3. dl: 描述列表, dt: 描述术语, dd: 描述细节"

    description list

    包含一组 术语 (`<dt>`) 和 描述 (`<dd>`) 的列表。此元素的常见用法是实现词汇表 (glossary) 或显示元数据（键值对列表）。

    description term

    必须在 `<dl>` 内使用
    
    description details


??? note "4. pre: 预定义格式文本"

    preformatted text

    通常使用 等宽字体(monospace) 渲染文本。

    保留空格，换行，Tab


!!! note "5. hr: horizontal rule"

!!! note "6. blockquote: 块级引用 block quotation"

!!! note "7. p: 段落 paragraph"

!!! note "8. div: 内容划分 content division"


### 2.2 inline

??? note "1. br: 换行"

    line break

    请勿用 `<br>` 在段落之间创建 margin；将它们 wrap 在 `<p>` 元素中，并使用 CSS margin 属性控制它们的大小。

    应该使用 `line-height` 属性(property) 增加文本之间的行间距。


!!! note "2. a: 锚 anchor"

!!! note "3. em: 强调 emphasis"

!!! note "4. strong: 重要"

    strong importance, seriousness, or urgency.

??? note "5. code: inline code"

    默认情况下, 它以浏览器的默认等宽字体 (monospace) 显示.

    要表示多行代码，请将 `<code>` 元素 wrap 在一个 `<pre>` 元素内。 `<code>` 本身只表示代码行 或 代码的单个短语。

    可以为 code 选择器定义 CSS 规则，以覆盖浏览器的默认字体。用户设置的首选项可能优先于指定的 CSS。

!!! note "6. q: 内联引用 inline quotation"

!!! note "7. span"
