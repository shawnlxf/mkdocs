
[transform playground](https://css-transform.moro.es/)

## 1 property

??? note "z-index"

    Overlapping elements with a larger z-index cover those with a smaller one.

    z-index CSS 属性 (property) 设置一个定位元素 (positioned element) 及其后代 或 Flex items 的 z-order。当元素之间重叠的时候，z-index 较大的元素会覆盖较小的元素。

    * auto: 盒子不会建立新的本地堆叠上下文。当前堆叠上下文中生成的盒子的 stack level 与其父级盒子相同。
    * <integer>: This <integer> is 在当前堆叠上下文中生成的盒子的 stack level. 该盒子还建立了一个 stack level 为0的 本地堆叠上下文。这意味着后代的 z-indexes 不会与该元素的外部元素的 z-indexes 进行比较。



??? note "text-align"

    The text-align CSS property 设置 块元素 或 table-cell box 的水平对齐。
    
    这意味着它的工作方式像 vertical-align 但是在水平方向。

??? note "vertical-align"

    vertical-align CSS 属性 (property) 设置 an inline, inline-block or table-cell box 的垂直对齐.

    在两种情况下使用：

    * To vertically align an inline element's box inside its containing line box. For example, it could be used to vertically position an <img> in a line of text
    * To vertically align the content of a cell in a table

    Line-relative values: 将元素相对于整行垂直对齐
    * top: 将 元素及其后代元素 的顶部与整行的顶部对齐。
    * bottom: 将 元素及其后代元素 的底部与整行的底部对齐。
    对于没有基线 (baseline) 的元素，将使用 bottom margin edge 代替。


??? note "使块本身居中而不使行内内容居中的标准兼容方法是将 left 和 right margin 设置为 auto，例如："

    ``` css
    .something {
      margin: auto;
    }
    ```

    ``` css
    .something {
      margin: 0 auto;
    }
    ```

    ``` css
    .something {
      margin-left: auto;
      margin-right: auto;
    }
    ```

??? note "line-height"

    设置 line box 的高度。通常用于设置文本行间距。
    
    对于块级元素，它指定元素行盒（line boxes）的最小高度。

    对于非替代 (non-replaced) 的 inline 元素，它指定用于计算行盒（line box）高度的高度。

??? note "white-space"

    设置如何处理元素中的 white space。

    nowrap

??? abstract "overflow"

    shorthand property: overflow-x, overflow-y

    设置 元素溢出所期望的行为

    overflow 属性被指定为从下面的值列表中选择的一个或两个关键字。如果指定了两个关键字，则第一个应用于 overflow-x，第二个应用于 overflow-y。否则，overflow-x 和 overflow-y 都被设置为相同的值。

    * visible (初始值)
    * hidden
    * scroll
    * auto

        取决于 用户代理。

        如果内容适合 padding box，则其看起来与 visible 相同，但仍会建立新的 块格式上下文 (block formatting context)。如果内容溢出，桌面浏览器会提供滚动条。

    ??? note "描述"

        指定非 visible (默认) 值将创建一个新的块格式化上下文
        
        为了 overflow 产生效果，块级容器必须具有设置的高度（height 或 max-height）或 white-space 设置为 nowrap。
        
        将一个轴设置为 visible（默认），而将另一个轴设置为不同的值将导致 visible 表现为 auto。

??? note "text-overflow"

    * 常用搭配：

        ``` css
        overflow: hidden;
        white-space: nowrap;
        ```

    text-overflow 属性仅影响沿其内联进度方向溢出了块容器元素的内容（例如，不是在盒子底部溢出的文本）。

    text-overflow 属性可以使用一个或两个值来指定。如果给出一个值，则它指定行尾的溢出行为（左到右文本的右端，右到左文本的左端）。如果给出两个值，则第一个指定行左端的溢出行为，第二个指定行右端的溢出行为。

    * clip (初始值)
    * ellipsis



??? note "[position](https://developer.mozilla.org/en-US/docs/Web/CSS/position)"

    position 属性设置元素在文档里如何定位. top, right, bottom, 和 left 属性决定 positioned elements 的最终位置.

    ??? note "position 属性被指定为从下面的值列表中选择的单个关键字。"

        * static (默认值)

            > 根据文档的 normal flow 定位元素。top，right，bottom，left，和 z-index 属性无效。

        * relative

            > 该元素根据文档的 normal flow 定位，然后基于 top，right，bottom，和 left 的值 相对于自身偏移。偏移量不会影响任何其他元素的位置；因此，页面布局中为元素提供的空间与 position 为 static 时相同。
            >
            > 当 z-index 值不为 auto 时，此值创建一个新的堆叠上下文。其在 table-*-group, table-row, table-column, table-cell, table-caption 元素的效果是 undefined。

        * absolute

            > 该元素已从 normal 文档流 中删除，并且在页面布局中没有为该元素创建空间。相对于其最接近的 positioned 祖先（如果有）定位；否则，它相对于初始包含块 (ICB, 文档根元素的包含块) 定位。其最终位置是由 top，right，bottom，和 left 的值决定的。
            >
            > 当 z-index 值不为 auto 时，此值创建一个新的堆叠上下文。绝对定位盒的 margin 不会与其他 margin 折叠。

        * fixed

            > 该元素从 normal 文档流中删除，并且在页面布局中没有为该元素创建空间。它相对于 由 viewport 建立的初始包含块定位，除了当它的祖先中的一个 具有 值不为 none 的 transform，perspective 或 filter 属性，在这种情况下祖先表现为包含块。其最终位置是由 top，right，bottom，和 left 的值决定的。
            >
            > 此值总是创建一个新的堆叠上下文。

        * sticky

            > 该元素根据文档的 normal flow 定位，然后基于 top，right，bottom，和 left 的值 相对于它的 最近的滚动祖先 和 包含块（最接近的块级祖先） 偏移，包括 table 相关的元素。该偏移量不会影响任何其他元素的位置。
            >
            > 此值总是创建一个新的堆叠上下文。注意，a sticky element "sticks" to 其最近的具有 "滚动机制" 的祖先（当 overflow 是 hidden，scroll，auto，或 overlay 时创建），即使祖先不是最近的实际滚动祖先。这有效地阻碍了任何 “sticky” 行为（[issues](https://github.com/w3c/csswg-drafts/issues/865)）。


    ??? abstract "定位类型" 

        ??? note "positioned element (定位元素)"

            > 其计算值是 relative, absolute, fixed, 或 sticky. (换句话说, 除了 static 的所有东西.)


            * relatively positioned element (相对定位元素)

                > 计算值: relative. 
                > 
                > top 和 bottom 属性(properties) 指定从其 normal 位置垂直偏移; left 和 right 属性(properties) 指定 水平偏移.

            * absolutely positioned element (绝对定位元素)

                > 计算 position 值：absolute 或 fixed。
                > 
                > top，right，bottom，和 left 属性指定 从元素的包含块的边缘的偏移量。(The containing block is the ancestor relative to which the element is positioned.) 如果元素具有 margins，则将它们添加到偏移量中。该元素为其内容建立一个新的块格式化上下文（BFC）。

            * stickily positioned element (粘性定位元素)


                > 计算 position 值：sticky
                >
                > 它被视为相对定位，直到其包含块 在其 flow root（或在其内滚动的容器）内超过指定的阈值（例如，设置 top 为 除了 auto 的值）为止，这个点将其视为 “stuck”，直到遇到 其包含块 的另一边的边缘。
                >
                > 粘性定位可以看作是 相对定位 和 固定定位 的混合体。粘性定位元素被视为相对定位，直到其超过指定的阈值为止，在该点处，该元素被视为 fixed，直到到达其父元素的边界为止。
                >
                > 为了使粘性定位的行为符合预期，你必须为粘性定位指定一个阈值，阈值为 top，right，bottom，或 left 中至少一个。否则，将无法与 相对定位 区分开。


        大多数情况下，height 和 width 被设置为 auto 的绝对定位元素，会调整大小以适应其内容。但是，non-replaced 的绝对定位元素可以通过指定 top 和 bottom ，并保留 height 为 unspecified（即 auto），来填充可用的垂直空间。它们同样可以通过指定 left 和 right 并将 width 保留为 auto 来填充可用的水平空间。

        除了刚刚描述的情况（绝对定位元素填充可用空间）之外：

        * 如果同时指定 top 和 bottom (technically, not auto)，则 top 获胜。
        * 如果同时指定 left 和 right，当方向是 ltr（英语，水平日语等）左胜；当方向是 rtl（波斯语，阿拉伯语，希伯来语等）右胜。


        ??? note "Performance & Accessibility"

            包含 fixed 或 sticky 内容的滚动元素可能会导致 性能 和 可访问性 问题。当用户滚动时，浏览器必须在新位置重新绘制 sticky 或 fixed 内容。根据需要重画的内容，浏览器的性能 以及 设备的处理速度，浏览器可能无法以 60 fps 的速度管理重画，从而给敏感人群带来可访问问题 和 所有人带来 jank (无响应)。一种解决方案是在 positioned elements 上添加 will-change: transform 以在其自己的图层中渲染该元素，从而提高了重新绘制速度，因此提高了性能和可访问性。


    2. float

        > 它把一个元素放在其容器的左边或右边，让 文本 和 内联元素 环绕它
        >
        > 从 normal flow 中移除该元素，尽管该元素仍然保留了一部分 flow (对比 absolute positioning).

    看 包含块 的例子


## 2 function

??? note "calc()"

    calc() CSS 函数让你在指定 CSS 属性 (property) 值时执行计算。 It can be used anywhere a `<length>`, `<frequency>`, `<angle>`, `<time>`, `<percentage>`, `<number>`, or `<integer>` is allowed.

    ``` css
    /* property: calc(expression) */
    width: calc(100% - 80px);
    ```

    作为参数的表达式 可以是 任何简单表达式 结合 以下运算符:

    +, -, *, /





