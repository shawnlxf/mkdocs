
## 1 认识 jQuery

??? note "JavaScript 自身存在 3个弊端"

    * 即复杂的文档对象模型（DOM）、
    * 不一致的浏览器实现和便捷的开发、
    * 调试工具的缺乏。

??? note "jQuery 的优势"

    1. 轻量级
    2. 强大的选择器
    3. 出色的 DOM 操作的封装
    4. 可靠的事件处理机制

        > jQuery 的事件处理机制吸收了 JavaScript 专家 Dean Edwards 编写的事件处理函数的精华，使得 jQuery 在处理事件绑定的时候相当可靠。在预留退路（graceful degradation）、循序渐进以及非入侵式（Unobtrusive）编程思想方面，jQuery 也做得非常不错。

    5. 完善的 Ajax
    6. 不污染顶级变量

        > jQuery 只建立一个名为 jQuery 的对象，其所有的函数方法都在这个对象之下。其别名 $ 也可以随时交出控制权，绝对不会污染其他的对象。该特性使 jQuery 可以与其他 JavaScript 库共存，在项目中放心地引用而不需要考虑到后期可能的冲突。

    7. 出色的浏览器兼容性
    8. 链式操作方式
    9. 隐式迭代

        > 当用 jQuery 找到带有 “.myClass” 类的全部元素，然后隐藏它们时，无需循环遍历每一个返回的元素。相反，jQuery 里的方法都被设计成自动操作对象集合，而不是单独的对象，这使得大量的循环结构变得不再必要，从而大幅地减少了代码量。

    10. 行为层与结构层的分离
    11. 丰富的插件支持

* window.onload 与 $(document).ready() 的对比

??? note "jQuery 对象 和 DOM 对象"

    1. DOM 对象

        可以通过 JavaScript 中的 getElementsByTagName 或者 getElementById 来获取元素节点。
        
        像这样得到的 DOM 元素就是 DOM 对象。

        ``` javascript
        let variable = DOM 对象;
        ```

    2. jQuery 对象

        jQuery 对象就是通过 jQuery 包装 DOM 对象后产生的对象。

        ``` javascript
        let $variable = jQuery 对象;
        ```

??? note "jQurey 对象和 DOM 对象的相互转换"

    1．jQuery 对象转成 DOM 对象

        两种方法：即 [index] 和 get(index) 。

    2．DOM 对象转成 jQuery 对象

        $(DOM对象)


## 2 jQuery选择器

> 选择器是 jQuery 的根基，在 jQuery 中，对事件处理、遍历 DOM 和 Ajax 操作都依赖于选择器。如果能熟练地使用选择器，不仅能简化代码，而且可以达到事半功倍的效果。

??? abstract "jQuery 选择器的优势"

    ??? note "1．简洁的写法"

        $("#ID") 用来代替 document.getElementById() 函数，即通过 ID 获取元素；
        
        $("tagName") 用来代替 document.getElementsByTagName() 函数，即通过标签名获取 HTML 元素

    ??? note "2. 完善的处理机制"

        即使用 jQuery 获取网页中不存在的元素也不会报错

        需要注意的是，$('#tt') 获取的永远是对象，即使网页上没有此元素。

        因此当要用 jQuery 检查某个元素在网页上是否存在时，不能使用以下代码：

        ``` javascript
        if ( $("#tt") ) {
            // do something
        }
        ```
    
        而应该根据获取到元素的长度来判断:

        ``` javascript
        if ( $("#tt").length > 0 ) {
            // do something
        }
        ```
    
        或者转化成 DOM 对象来判断:

        ``` javascript
        if ( $("#tt")[0] ) {
            // do something
        }
        ```

??? abstract "Selectors (选择器)"

    ??? note "1. Basic (基础选择器)"

        ![](../img/Books/选择器-基础.jpg)

    ??? note "2. Hierarchy (层级)"

        ![](../img/Books/选择器-层级.jpg)

        在层次选择器中，第1个和第2个选择器比较常用，而后面两个因为在 jQuery 里可以用更加简单的方法代替，所以使用的几率相对少些。

        $(".one + div"); 等价于 $(".one").next("div");

        $("#prev~div"); 等价于 $("#prev").nextAll("div");

    ??? note "3. 过滤"

        1. 基础过滤

            ![](../img/Books/选择器-基础过滤.jpg)

        2. 内容过滤

            ![](../img/Books/选择器-内容过滤.jpg)

        3. 可见性过滤

            ![](../img/Books/选择器-可见性过滤.jpg)

        4. 属性过滤

            ![](../img/Books/选择器-属性过滤.jpg)

        5. 子元素过滤

            ![](../img/Books/选择器-子元素过滤.jpg)

    ??? note "4. 表单"

        ![](../img/Books/选择器-表单-1.jpg)
        ![](../img/Books/选择器-表单-2.jpg)



