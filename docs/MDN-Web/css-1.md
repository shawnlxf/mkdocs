
> [reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)

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




