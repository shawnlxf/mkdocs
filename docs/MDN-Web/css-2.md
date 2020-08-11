

??? note "[Viewport (视口) 概念](https://developer.mozilla.org/en-US/docs/Web/CSS/Viewport_concepts)"

    视口表示计算机图形中正在被查看(view)的区域。

??? note "[Block formatting context (块格式化上下文)](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context)"

    It's the region in which the layout of block boxes occurs and in which floats interact with other elements.

??? note "[The stacking context (层叠上下文)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context)"

??? note "[containing block (包含块)](https://developer.mozilla.org/en-US/docs/Web/CSS/Containing_Block)"

    元素的大小和位置 经常受它的 包含块 的影响，因为 width, height, padding, margin 的百分值 和 绝对定位元素(absolute 或 fixed)的offset properties 从 元素的包含块 计算得来

    当浏览器 lay out a document 时, 它给每一个元素生成一个 box

??? abstract "值"

    指定值（包含初始值） + 计算 = 计算值

    ??? note "[Initial value (初始值)](https://developer.mozilla.org/en-US/docs/Web/CSS/initial_value)"

        default value (默认值)

        不要与浏览器的 style sheet 指定的值 混淆

    ??? note "[Specified value (指定值)](https://developer.mozilla.org/en-US/docs/Web/CSS/specified_value)"

        * CSS property 的指定值是从 document's style sheet 接收的值.
        * ruls:

            1. style sheet 明确指定
            2. style sheet 没有指定 但是是继承的 property，从父元素获取
            3. 以上都不是，使用 initial value

    ??? note "[Computed value (计算值)](https://developer.mozilla.org/en-US/docs/Web/CSS/computed_value)"

        CSS property 的计算值是 
        
        * when：在继承时从父到子转移的值
         
        * how: 从 specified value 计算得出 




