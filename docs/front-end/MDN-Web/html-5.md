# inline 和 block level

## 1 [Inline elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements)

??? note "Changing element levels"

    您可以使用 CSS display property 更改元素的 visual presentation。例如，通过将 display 的值从"inline"更改为"block"，可以告诉浏览器将内联元素渲染在 block box 里而不是 inline box，反之亦然。但是，这样做不会更改元素的 category (类别)  和 content model (内容模型)。例如，即使将 span 元素的 display 更改为 "block"，也仍然不允许在其中嵌套 div 元素。

??? note "概念差异"

    * Content model (内容模型)

        通常，内联元素只能包含 数据 (data) 和 其他内联元素。您不能将块元素放入内联元素中。

    * Formatting (格式化)

        默认情况下，内联元素不会强制在文档流中开始新的一行。另一方面，块元素通常会导致换行（line break, 尽管通常可以使用 CSS 进行更改）。


## 2 [Block-level elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements)

* 块级元素只能出现在 `<body>` 元素内。

??? note "关键区别"

    * Content model (内容模型)

        通常，块级元素可能包含内联元素和（有时）其他块级元素。

    * Default formatting (默认格式)

        默认情况下，块级元素从新行开始，但是内联元素可以在一行中的任何地方开始。

??? note "[Content categories](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories)"

    "inline" category 大致对应于 phrasing content (措辞内容) category, “块级”类别并不直接对应于任何 HTML5 内容类别

    但是组合在一起的 "block-level" 和 "inline" 元素对应于 HTML5 中的 flow content (流内容)。还有其他类别，例如 interactive content (交互式内容)。





