
??? note "[Viewport (视口) 概念](https://developer.mozilla.org/en-US/docs/Web/CSS/Viewport_concepts)"

    > 本文解释了视口的概念 - 它是什么，以及它在 CSS，SVG 和 移动设备 方面的影响，并区分了 visual viewport 和 layout viewport。

    概括地说，viewport 基本上是文档的当前可见部分。


??? abstract "[containing block (包含块)](https://developer.mozilla.org/en-US/docs/Web/CSS/Containing_Block)"

    元素的大小和位置 经常受其 包含块 影响。通常，包含块是元素最接近的块级祖先的内容区域 (content area)，但并非总是如此。
    
    ??? note "包含块 的影响"

        元素的大小和位置经常受其包含块的影响。应用到 width，height，padding，margin，和 绝对定位元素（也就是说，position 设为 absolute 或 fixed）的 offset 属性 的百分比值 从元素的包含块计算得来。

    ??? note "识别 包含块"

        识别 包含块 的过程完全取决于元素的 position 属性的值：

        1. 如果 position 属性是 static，relative 或 sticky，则 包含块 由最近的祖先元素的 content box 的边缘形成，该元素是一个块容器（例如 inline-block，block 或 list-item 元素）或 建立一个 格式化上下文（例如表 (table) 容器，伸缩 (flex) 容器，网格 (grid) 容器 或 块 (block) 容器本身）。

        2. 如果 position 属性是 absolute，包含块 由最近的祖先元素的 padding box 的边缘形成，该元素的 position 值不是 static（即 fixed，absolute，relative，或 sticky）。

        3. 如果 position 属性是 fixed，则 包含块 由 视口（viewport, 对于连续媒体 continuous media 而言）或 页面区域（page area, 对于分页媒体 paged media 而言）建立。

        4. 如果 position 属性为 absolute 或 fixed，则包含块也可能由 最近的祖先元素的 padding box 的边缘 形成，该元素具有以下内容：

            1. A transform or perspective value other than none
            2. A will-change value of transform or perspective
            3. A filter value other than none or a will-change value of filter (only works on Firefox).
            4. A contain value of paint (e.g. contain: paint;)

        ??? note "Note"

            根元素（`<html>`）所在的 包含块 是一个称为 初始 (initial) 包含块 的矩形。它具有视口（用于连续媒体 continuous media）或 页面区域（page area, 用于分页媒体 paged media）的尺寸。

    ??? note "从包含块计算百分比值"

        are box model properties and offset properties:

        如上所述，当给某些属性指定百分比值时，其计算值 取决于元素的包含块。以这种方式工作的属性是 盒模型属性 (box model properties) 和 偏移属性 (offset properties)：

        1. height, top, 和 bottom 属性 从 包含块的 height 计算百分比值.
        2. width, left, right, padding, 和 margin 属性 从 包含块的 width 计算百分比值.

    ...



??? abstract "[Block formatting context (块格式化上下文)](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context)"


    块格式化上下文 是 网页的视觉 CSS 渲染的一部分。

    在该区域中，block boxes 的布局发生 (occur)，并且 floats 会与其他元素相互作用。

    ??? note "块格式化上下文 由以下至少其中之一创建："

        1. 文档的根元素（`<html>`）
        * Floats (浮动元素, 元素的 float 不是 none)
        * 绝对定位元素 (元素的 position 是 absolute 或 fixed)
        * Inline-blocks (elements with display: inline-block)
        * Table cells (elements with display: table-cell, 这是 HTML table cells 的默认值)
        * Table captions (elements with display: table-caption, 这是 HTML table captions 的默认值)
        * 块元素的 overflow 的值不是 visible
        * Flex items (弹性元素，direct children of the element with display: flex or inline-flex) 如果它们本身既不是 flex 也不是 grid 或 table 容器。
        * Grid items (网格元素，direct children of the element with display: grid or inline-grid) 如果它们本身既不是 flex 也不是 grid 或 table 容器。


    格式化上下文 会影响布局，但是通常，我们为 定位 (positioning) 和 清除浮动元素(clearing floats) 创建新的块格式化上下文，而不是更改布局，因为建立新的块格式化上下文的元素将：

    * 包含内部 floats.
    * 排除外部 floats.
    * 抑制 margin collapsing.

    ??? note "Note"

        Flex/Grid 容器（display：flex/grid/inline-flex/inline-grid）建立新的 Flex/Grid 格式化上下文，除了布局外，它与 块格式化上下文 相似。在 flex/grid 容器内部不能用 floating children，但是排除外部 floats 和 抑制 margin collapsing 仍然有效。


??? note "[The stacking context (堆叠上下文)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context)"

    ??? note "在以下情况，会形成堆叠上下文："

        1. 文档的根元素（`<html>`）
        * Element with a position 值为 absolute 或 relative 且 z-index 值不为 auto.
        * Element with a position 值为 fixed 或 sticky (sticky for 所有移动浏览器, 但不适用于较旧的桌面).
        * Element 是 flex (flexbox) 容器的子元素, 且 z-index 值不为 auto.
        * Element 是 grid (grid) 容器的子元素, 且 z-index 值不为 auto.
        * Element with opacity 值小于1.
        * Element with 以下任一属性 (properties) 的值不为 none:

            * transform
            * filter
            * perspective
            * clip-path
            * mask / mask-image / mask-border

    重要的是，其子级堆叠上下文的 z-index 值只在父级中才有意义。子级堆叠上下文被自动视为父级堆叠上下文的一个独立单元。

    ??? abstract "In summary"

        * 堆叠上下文可以包含在其他堆叠上下文中，并一起创建堆叠上下文的层次结构。
        * 每个堆叠上下文完全独立于其同级 (siblings)：处理堆叠时仅考虑后代元素 (descendant elements)。
        * 每个堆叠上下文都是自包含的：在元素的内容堆叠之后，将按照父堆叠上下文的堆叠顺序考虑整个元素。

    ??? note "Note"

        堆叠上下文的层次结构是 HTML 元素层次结构的子集，因为只有某些元素才会创建堆叠上下文。可以这样说，没有创建自己的堆叠上下文的元素会被 父堆叠上下文 同化。




??? abstract "值"

    指定值 (包含初始值，继承值) 一部分变为 计算值 (计算完成变为 应用值)

    ??? note "[Initial value (初始值)](https://developer.mozilla.org/en-US/docs/Web/CSS/initial_value)"

        默认值

        初始值的使用取决于属性是否被继承：

        * 对于 继承属性，只要不提供 指定值，则只能在根元素上使用初始值。
        * 对于 非继承属性，只要不提供 指定值，可以在所有元素上使用初始值。

        可以使用 initial 关键字显式指定初始值。

        !!! important "请勿将初始值与浏览器的样式表指定的值混淆。"


    ??? note "[Specified value (指定值)](https://developer.mozilla.org/en-US/docs/Web/CSS/specified_value)"

        CSS 属性 (property) 的指定值是从 文档的样式表 接收的值.

        给定属性的指定值 是由以下规则决定的：

        1. 如果文档的样式表明确指定属性的值，则将使用给定的值。
        2. 如果文档的样式表未指定值，但它是继承属性，则该值将从父元素中获取。
        3. 如果以上都不是，将使用元素的初始值。


    ??? note "[Computed value (计算值)](https://developer.mozilla.org/en-US/docs/Web/CSS/computed_value)"

        CSS 属性 (property) 的计算值 是继承过程中 从父到子 转移的值。它从指定值计算得来：

        1. 处理特殊值 inherit, initial, unset, 和 revert.
        2. 进行计算以达到属性定义表中 “计算值” 行中描述的值。

        达到属性的计算值所需的计算 通常包括 将相对值（例如以 em 单位 或 百分比 表示）转换为 绝对值。例如，如果一个元素有指定的值 font-size: 16px 和 padding-top: 2em，则 padding-top 的计算值是 32px（字体大小的两倍）。

        然而，对于一些属性（那些其中的百分比 是 相对于 可能需要布局来决定的 sth，例如 width，margin-right，text-indent，和 top），百分比指定 (percentage-specified) 值 变成 百分比计算 (percentage-computed) 值。此外，在 line-height 属性上指定的无单位数字 将成为指定的计算值。保留在计算值中的相对值 会在应用值确定后成为 绝对值。

    ??? note "[Used value (应用值)](https://developer.mozilla.org/en-US/docs/Web/CSS/used_value)"

        CSS 属性 (property) 的应用值（used value）是 计算值 完成所有计算后的值

        用户代理完成计算后，每个 CSS 属性有一个应用值。尺寸的应用值（例如 width，line-height）以像素为单位。速记 (shorthand) 属性（例如 background）的应用值与其组件 (component) 属性（例如 background-color 或 background-size）一致 and with `position` and `float`。

        !!! note "注意：`getComputedStyle()` DOM API 返回解析值 (resolved value)，其可以是 计算值 或 应用值，具体取决于属性。"

        ...


    ??? note "[Resolved value (解析值)](https://developer.mozilla.org/en-US/docs/Web/CSS/resolved_value)"

        CSS 属性 (property) 的解析值 是 `getComputedStyle()` 的返回值。

        对于大多数属性，它是计算值，但对于一些旧属性（包括 width 和 height），则是 应用值。


    ??? note "[Actual value (实际值)](https://developer.mozilla.org/en-US/docs/Web/CSS/actual_value)"

        CSS 属性的 实际值 是该属性的 应用值 经过必要的近似之后得到的。例如，只能渲染具有整数像素宽度的 border 的用户代理 可能将 border 的厚度四舍五入到最接近的整数。

        用户代理执行四个步骤 计算属性的 实际 (final) 值：

        1. 基于 级联 (cascading) 的结果, 继承 或 使用初始值 决定指定值 
        2. 根据规范 (specification) 计算得出 计算值 (例如，a span with position: absolute will have its computed display changed to block)
        3. 计算布局，得出 应用值
        4. 根据本地环境的限制对 应用值 进行转换，得出 实际值。




[cascade](https://developer.mozilla.org/en-US/docs/Web/CSS/Cascade)