
## 2 [CSS 构建块(building blocks)](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks)

### 2.1 层叠与继承 (Cascade and inheritance)

??? note "继承 (Inheritance)"

    一些属性 (properties) 是不能继承的，很大程度上由常识决定的。

    举个例子: 如果你在一个元素上设置 width 为 50% ，所有的后代不会是父元素的宽度的50% 。如果这个也可以继承的话，CSS就会很难使用了!

    像 widths (上面提到的), margins, padding, 和 borders 不会被继承。

??? note "控制继承"

    CSS提供了四个特殊的通用属性值来控制继承。每个CSS属性都接受这些值。

    1. inherit

        > 使 选定元素 的属性值和父元素相同。实际上，就是 "开启继承".

    2. initial

        > 设置 选定元素 的属性值 为 该属性的初始值

    3. unset

        > 将属性重置为其自然值。这意味着，如果该属性是自然继承的，则其行为类似于inherit，否则，其行为类似于initial。
    
    !!! note "注: 还有一个新的属性, revert，只有很少的浏览器支持。"

??? note "重置所有属性值"

    CSS速记属性all可用于一次将这些继承值之一应用于（几乎）所有属性。其值可以是继承值中的任何一个（inherit，initial，unset，或revert）。这是撤消对样式所做的更改的便捷方法，以便您可以在开始新的更改之前回到已知的起点。

    ``` css
    .fix-this {
        all: unset;
    }
    ```

* 理解层叠 (cascade)

    要考虑三个因素，这里按重要性从高到低的顺序列出。前面的否决后面的

    1. Importance
    2. Specificity

        ??? note "a class selector has more weight (权重) than an element selector"

            此行为有助于避免CSS中的重复。一种常见的做法是为基本元素定义通用样式，然后为那些不同的元素创建类。

        ??? abstract "一个选择器具有的特定性总数是使用四个不同的值（或分量 components）来衡量的，可以看做 "千，百，十，个""

            1. 千位：如果声明在 style 的属性（内联样式）内，则该位得一分。这样的声明没有选择器，所以特定性总是1000。
            2. 百位：整体的选择器中包含的每个 ID 选择器，则该位得一分。
            3. 十位：整体的选择器中包含的每个 类(class)选择器、属性(attribute)选择器 或者 伪类(pseudo-class)，则该位得一分。
            4. 个位：整体的选择器中包含的每个 元素(element)选择器、伪元素(pseudo-element)，则该位得一分。

            !!! note "Note: The universal selector (*), combinators (+, >, ~, ' '), and negation pseudo-class (:not) have no effect on specificity."

            ??? note "评估特异性的更准确方法是对特异性水平分别评分，从最高开始，必要时(平局)降低到最低。"

                实际上，每种选择器类型都有其自己的特定性，不能被较低特定性级别的选择器覆盖。例如，组合在一起的一百万个 class 选择器将无法覆盖一个 id 选择器的规则。


    3. Source order






### 2.2 CSS选择器


CSS 选择器规定了 CSS 规则会被应用到哪些元素上。

??? abstract "1 基本选择器 (Basic selectors)"

    ??? note "1.1 通用选择器（Universal selector）"

        > 选择所有元素。
        >
        > 语法：`*`

        ``` css
        /* 使选择器更易读 */
        /* 选择 <article\> 元素后代元素中的第一个孩子 */
        article *:first-child { 

        } 
        ```

    ??? note "1.2 类型选择器（Type selector, 个）"

        > 选择具有给定节点名称的所有元素。
        >
        > 语法：`elmentname`

    ??? note "1.3 类选择器（Class selector, 十）"

        > 选择具有给定 class 属性的所有元素。
        >
        > 如果元素被应用了两个类，只需将它们链接 (chaining) 在一起并且它们之间没有空格，便可以匹配该元素。
        >
        > 语法：`.classname`

        ``` css
        .notebox.danger {
          border-color: red;
          font-weight: bold;
        }
        ```

    ??? note "1.4 ID 选择器（ID selector, 百）" 

        > 根据其 id 属性值选择一个元素。文档中应只有一个具有给定 ID 的元素。
        >
        > 可以在ID之前添加类型选择器
        >
        > 语法：`#idname`

        ``` css
        h1#heading {
            color: rebeccapurple;
        }
        ```

        ??? note

            ID 具有很高的 specificity，并且会推翻大多数其他选择器。所以很难处理它们。在大多数情况下，最好是在元素中添加 class 而不是使用 ID，但是，如果使用 ID 是指定元素的唯一方法（也许是因为您无权访问标记，因此无法对其进行编辑），这会生效。

    ??? note "1.5 属性选择器（Attribute selector, 十）"

        > 选择具有给定属性的所有元素。
        >
        > 语法：`[attr]`, `[attr=value]`
        >
        > 例：`a[title] { }`

        ```
        // 匹配具有 attr 属性的元素，该元素的值恰好是 value，或者在其（空格分隔的）值列表中包含 value。
        [attr~=value]
        // 匹配具有 attr 属性的元素，该属性的值恰好是 value 或 以 value 开头，之后紧跟一个连字符。
        [attr|=value]
        ```

        ??? note "子字符串匹配选择器"

            ```
            // 属性的值以 "box-" 开头
            li[class^="box-"]  (or [class|="box"])
            // 属性的值以 "-box" 结尾
            li[class$="-box"]
            // 属性的值在字符串中的任何位置包含了 "box"。
            li[class*="box"]
            ```

        ??? note "大小写敏感"

            如果要不区分大小写地匹配属性值，则可以在右括号 (closing bracket) 之前用 i 。
            
            > 如果没有标记，则值将根据文档语言的 case-sensitivity 进行匹配--在 HTML 中将区分大小写。

            ``` css
            li[class^="a" i] {
                color: red;
            }
            ```



??? note "2 分组选择器 (Grouping selectors)"

    * 选择器列表（Selector list）

        > 语法：`A, B`

??? note "3 组合器 (Combinators)"

    * 后代组合器（Descendant combinator）

        > 选择前一个元素的后代节点。
        >
        > 语法：`A B`

    * 直接子代组合器（Child combinator）

        > 选择第一个元素的直接子代的节点。
        >
        > 语法：`A > B`

    * 一般兄弟组合器（General sibling combinator）

        > 选择兄弟元素，这意味着第二个元素在第一个元素后面的任意位置，并且共享相同的父元素。
        >
        > 语法：`A ~ B`

    * 紧邻兄弟组合器（Adjacent sibling combinator）

        > 选择相邻的兄弟元素。这意味着第二个元素直接跟随第一个元素，并且共享相同的父元素。
        >
        > 语法：`A + B`

??? note "4 伪选择器 (Pseudo)"

    * 伪类 (Pseudo classes, 十)

        > 允许基于不包含在 document tree 的状态信息 来选择元素
        >
        > 例子: `a:visited`

    * 伪元素 (Pseudo elements, 个)

        > 表示无法用 HTML 语义表达的实体。
        >
        > 选择元素的某一部分而不是元素自身
        >
        > 例子: `p::first-line` 匹配所有 <p\> 元素的第一行


### 2.3 盒模型 (The box model)

### 2.4 Backgrounds and borders

### 2.5 处理不同的文本方向

### 2.6 溢出的内容

### 2.7 值和单位

### 2.8 调整项目大小 (Sizing items in CSS)

### 2.9 Images, media, and form (表单) elements

### 2.10 样式化表格 (Styling tables)

### 2.11 Debugging CSS

### 2.12 组织 CSS



## 3 [样式化文本(styling text)]()

## 4 [CSS 布局(layout)]()