
* property

??? note "text-align"

    The text-align CSS property 设置 块元素 或 table-cell box 的水平对齐。
    
    这意味着它的工作方式像 vertical-align 但是在水平方向。

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

??? note "overflow"

    shorthand property: overflow-x, overflow-y

    设置 元素溢出所期望的行为

    overflow 属性被指定为从下面的值列表中选择的一个或两个关键字。如果指定了两个关键字，则第一个应用于 overflow-x，第二个应用于 overflow-y。否则，overflow-x 和 overflow-y 都被设置为相同的值。

    * visible (初始值)
    * hidden
    * scroll
    * auto

        取决于 用户代理。

        如果内容适合 padding box，则其看起来与 visible 相同，但仍会建立新的 块格式上下文 (block formatting context)。如果内容溢出，桌面浏览器会提供滚动条。

        > 指定非 visible (默认) 值将创建一个新的块格式化上下文
        >
        > 为了 overflow 产生效果，块级容器必须具有设置的高度（height 或 max-height）或 white-space 设置为 nowrap。
        >
        > 将一个轴设置为 visible（默认），而将另一个轴设置为不同的值将导致 visible 表现为 auto。

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

    * Types (类型)

        * positioned element (定位元素)

            > 计算值不是 static

            * relatively positioned element (相对定位元素)

                > 计算值：relative

            * absolutely positioned element (绝对定位元素)

                > 计算值：absolute 或 fixed
                >
                > properties: top, right, bottom, left 的偏移从 包含块 计算得来

            * stickily positioned element (粘性定位元素)

                > 计算值：sticky
                >
                > 一般情况：relatve
                >
                > 特殊情况：在 container 里滚动 包含块超过 container 的边缘就粘住

    2. float

        > 它把一个元素放在其容器的左边或右边，让 文本 和 内联元素 环绕它
        >
        > 从 normal flow 中移除该元素，尽管该元素仍然保留了一部分 flow (对比 absolute positioning).




