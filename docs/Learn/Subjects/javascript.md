
## 1 路线：

* 1.1 -> 1.2 -> 2

    ??? note "1.1"

        * [阮一峰的 JS 教程](https://wangdoc.com/javascript/) (JS入门)
        * [阮一峰的 ES6 教程](https://es6.ruanyifeng.com/)
        * [现代 JavaScript 教程](https://zh.javascript.info/)

    ??? note "1.2"

        * MDN
        * 菜鸟教程
        * [JS 秘密花园](http://bonsaiden.github.io/JavaScript-Garden/zh/)
        * [学习指南](https://hijiangtao.github.io/2018/01/25/learn-plain-javascript-from-top-tutorials-for-the-past-year-v-2018/)
        * [ES6 新特性列表](https://fangyinghang.com/es-6-tutorials/)

        * [博客-haha](https://www.cnblogs.com/hahazexia/p/9446585.html)
        * [博客-郑馋师](https://www.jianshu.com/u/66bca46ceb07)

    ??? note "2"

        * 你不知道的 JavaScript (先看上卷，适合进阶)

* jQuery

    ??? note "mdn 定义"

        jQuery 是一个 JavaScript 库，致力于简化 DOM 操作，AJAX 调用 和 事件处理。

        jQuery 使用 `$(selector).action()` 的格式将(一个或多个)元素分配给事件。具体来说，`$(selector)` 将调用 jQuery 来选择 `selector` 元素，并将其分配给名为 `.action()` 的事件 API。

        ``` javascript
        $(document).ready(function(){
          alert("Hello World!");
          $("#blackBox").hide();
        });
        ```

        上述代码和以下代码功能相同：

        ``` javascript
        window.onload = function() {
          alert("Hello World!");
          document.getElementById("blackBox").style.display = "none";
        };
        ```

        或

        ``` javascript
        window.addEventListener("load", () => {
          alert("Hello World!");
          document.getElementById("blackBox").style.display = "none";
        });
        ```

    * [菜鸟教程](https://www.runoob.com/jquery/jquery-tutorial.html)
    * [jQuery API](https://api.jquery.com/)
    * [jQuery API 中文文档](https://www.jquery123.com/)
    * [jQuery 基础](http://jqfundamentals.com/)


* 常见错误

    * Uncaught SyntaxError: Invalid or unexpected token (字符串)