
## 1 [floats](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats)

float 属性 (property) 最初是用于在文本块内浮动图像，后来成为在网页上创建多列布局的最常用工具之一。随着 flexbox 和 grid 的出现，它现在又恢复了其原始用途。

在本文中，我们将只关注 floats 的正确用法。

??? note "float 的工作原理"

    设置了 float 的 元素将从文档的 normal 布局流中取出 (is taken out of) 并粘在 (is stuck to) 其​​父容器的左侧。normal 布局流中 位于浮动元素下方的所有内容现在都将环绕 (wrap) 在其周围，并填充 (fill up) 空间到其右侧，顶部和该浮动元素的顶部一样高。在那里，它将停止。

    将内容浮动到右侧具有完全相同的效果，但相反地 - 浮动的元素将粘在 (stick to) 右侧，而内容则将其环绕在左侧。

??? note "Clearing floats"

    如果我们要阻止下一个元素向上动 (move up)，则需要 clear it；这是通过 clear 属性 (property) 实现的。

    clear 属性 (property) 接收以下值:

    * left: Clear items floated to the left.
    * right: Clear items floated to the right.
    * both: Clear any floated items, left or right.

??? abstract "Clearing boxes wrapped around a float"

    想要盒子的底部 wrap the floated item and wrapping 内容，即使内容较短。

    有三种可能的方法可以解决此问题，其中两种可以在所有浏览器中使用 - 但有些 hacky - 第三种新方法可以正确处理这种情况。

    ??? note "1. The clearfix hack"

        传统上处理这种情况的方法是使用一种称为 "clearfix hack" 的东西。这 involves 在包含 float 和 wrapping content 的盒子后 插入一些生成的内容，并设置它来 clear both。

        ``` css
        .wrapper::after {
          content: "";
          clear: both;
          display: block;
        }
        ```

        本质上，这与 你在 items 下方加一个 HTML 元素例如 `<div>` ，并将其设置为 clear: both 相同。

    ??? note "2. 使用 overflow"

        另一种方法是将 wrapper 的 overflow 属性 (property) 设置为除了 visible 以外的值。

        加 `#!css overflow: auto` 到 wrapper 的规则 (rules)。

        这个例子通过 创建所谓的块格式化上下文（BFC） 来工作。这就像页面内部的一个迷你布局，其中包含 everything，因此浮动元素 (floated element) 包含在 BFC 中，背景在这两个 items 后面运行。这通常会起作用，但是，在某些情况下，由于使用 overflow 的意外结果，您可能会发现不想要的 滚动条 或 修剪的阴影 (clipped shadows)。

    ??? note "3. display: flow-root"

        解决这个问题的现代方法是使用 display 属性 (property) 的 flow-root 值。这是一个只是为了 不需要使用 hacks 就可以创建一个 BFC 的方法 - 使用它时不会有意外的后果。添加 `#!css display: flow-root` 到 .wrapper 规则中。假设你有支持的浏览器，盒子将 clear。


## 2 [Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)

Flexbox 是一种用于在行或列中布局 items 的一维布局方法。Items flex 以填充额外的空间，并收缩以适合更小的空间。本文介绍了所有基础知识。

??? abstract "常用 父 property"

    ??? note "在想要影响的元素的父元素上设置 `#!css display: flex`"

        这导致 `<section>` 元素成为 flex container, its children 成为 flex items.

        设置 `#!css display: flex` 的元素 在它与页面其余部分交互方面 表现地像块级元素，但是其子元素 (children) 作为 flex items 被布局。如果想让该元素的行为像 inline 元素，元素的 children 以 flex items 布局，请使用 `#!css display: inline-flex`。

    !!! note "flex-direction"
    !!! note "flex-wrap"
    ??? note "flex-flow (shorthand)"

        ``` css
        flex-flow: row wrap;
        ```

    ??? note "align-items"

        控制 flex items 在 cross axis 上的位置。

        * values

            * stretch (default)
            * center
            * flex-start / flex-end

    ??? note "justify-content"
    
        控制 flex items 在 main axis 上的位置。

        * flex-start (default)
        * flex-end
        * center
        * space-around (evenly, 两端留一些空间)
        * space-between (evenly, 两端不留空间)
    
??? abstract "常用 子 property"

    ??? note "flex"

        flex 是一个简写属性 (property) ，最多可以指定三个不同的值：

        * 无单位比例值。可以使用 flex-grow longhand 属性 单独指定。
        * 第二个无单位比例值 - flex-shrink - 当 flex items 溢出其容器时起作用。它指定从每个 flex items 的 size 中拿走多少溢出量，以阻止它们溢出其容器。这是相当高级的 flexbox 功能，我们将不在本文中进一步讨论。
        * 最小 size 值。可以使用 flex-basis longhand 值单独指定。

        除非你确实需要（例如，覆盖先前设置的 sth），否则建议不要使用 longhand flex 属性。它们导致编写了很多额外的代码，并且可能有些混乱。

        ``` css
        flex: 200px;
        ```

        ``` css
        article {
          flex: 1 200px;
        }

        article:nth-of-type(3) {
          flex: 2 200px;
        }
        ```

    !!! note "align-self"




??? question "Why Flexbox?"

    floats 和 positioning 在某些方面 有局限 和 frustrating。

    使用这种工具以任何方便，灵活的方式很难或不可能实现
    以下简单的布局需求用上面两种工具很难或无法以方便灵活的方式实现：

    * 在其父内部将一个内容块垂直居中。
    * Making all the children of a container take up an equal amount of the available width/height, regardless of how much width/height is available.
    * 使多列布局中的所有列都采用相同的高度，即使它们包含的内容量不同。


??? note "The flex model"

    当元素以 flex items 布局, 它们沿两个轴布局:

    ![](../img/MDN-Learn/flex_terms.png)


...



## 3 Positioning (定位)

??? note "z-index"

    定位元素 (positioned elements) 胜过 未定位元素 (non-positioned elements)

!!! note "Fixed positioning (固定定位)"
