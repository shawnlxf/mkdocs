# CSS

* [参考文档](https://developer.mozilla.org/en-US/docs/Web/CSS)
* [CSS 常见问题](https://developer.mozilla.org/en-US/docs/Learn/CSS/Howto)

## 1. [第一步](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps)

### 1.1 什么是 CSS

* 标记语言：HTML / SVG / XML

### 1.2 开始
### 1.3 CSS 的结构
### 1.4 CSS 如何工作
### 1.5 运用新知识

## 2. [CSS building blocks](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks)

    * [CSS values and units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)

        > 长度单位

        1. Lengths (长度, 最常遇到)

            1. relative

                > 相对于 something else, 如父元素的字体大小, 或视口的大小等
                > 可以让文本，或其他元素相对于 everything else 缩放

                * em: 元素本身的字体大小
                * rem: 根元素的字体大小
                * vw: 视口宽度的 1%
                * vh: 视口高度的 1%
                ...

            2. absolute

                * px

        2. Percentages
        3. Numbers


* position: absolute;

    > Elements that are relatively positioned remain in the normal flow of the document. 
    > 
    > In contrast, an element that is absolutely positioned is taken out of the flow.

* line-height
  
    > sets the height of a line box
    >
    > It's commonly used to set the distance between lines of text

* overflow
  
    > sets what to do when an element's content is too big to fit in its block formatting context
    >
    > a shorthand for overflow-x and overflow-y.
    >
    > * auto: Depends on the user agent

* clear
  
    >  sets whether an element must be moved below (cleared) floating elements that precede it

