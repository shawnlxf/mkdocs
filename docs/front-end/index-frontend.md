
* [前端导航](https://shawnlxf.github.io/nav-1/dist/index.html)
* [w3c 待办](https://www.w3schools.com/js/js_number_methods.asp)
* [w3c whatis](https://www.w3schools.com/whatis/whatis_http.asp)
* [Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools/)

??? info

    * 域名
    * 每日新增常见问题
    * 每日新增 w3c 总结
    * mdn-learn 继续

* 方方-前后端分离回顾
* this, class
* w3 JSON
* vim 技巧
* vscode 快捷键

!!! note "[打字训练](https://dytiger.github.io/index.html)"

??? abstract "学习途径"

    ??? note "1. 网上资料"

        1. 学习教程 (主体)

            * MDN
            * w3schools / 菜鸟

        2. 查询 / 博客 / 公众号 (查漏补缺): google 搜索 "前端 学习"

            * [php 中文网](https://www.php.cn/web-designer.html)
            * [廖雪峰](https://www.liaoxuefeng.com/)
            * javascript语言精粹
            * dom编程艺术
            * 网络编程(简单，搜索)：fetch, websocket, jsonp, cors, formData

                > AJAX 已经被 [Fetch Standard](https://fetch.spec.whatwg.org/) 取代，学习 fetch api 即可 

            * github 上的 4 个 star
            * 阮一峰的博客
            * 知乎的关注

    ??? note "2. 电子书 (PDF / 微信读书)"

        * (你不知道的JavaScript（上卷）)[https://book.douban.com/subject/26351021/] (JS 进阶)
        * 两本免费的 JS 教材《JavaScript 教程》《ECMAScript 6 入门》
        * 小黄书上卷
        * 高性能 javascript
        * 编写可维护的 javascript
        * 算法
        * 图解 http
        * 深入浅出 react 和 redux
        * javascript 编程精解
        * javascript 高级程序设计

    ??? note "3. 视频 (看项目实践)"

        * [哔哩哔哩（经验分享）](https://space.bilibili.com/143487021/fans/follow)
        * 慕课网
        * 饥人谷
        * youtube
        * [黑马项目](http://www.itcast.cn/course/web.shtml) | [尚硅谷](http://www.atguigu.com/web/)

??? abstract "学习分类"

    ??? note "HTML"

        > 不要买任何 HTML 的书
        > 
        > google: mdn html5

        * 1

            * MDN
            * [阮一峰的HTML教程](https://wangdoc.com/html/index.html)
            * 例子：w3schools / 菜鸟

    ??? note "CSS"

        > 不要买任何 CSS 的书
        >
        > Google 搜索关键词时加 MDN

        * 1

            * MDN
            * w3schools / 菜鸟
            * [CSS Tricks](https://css-tricks.com/)
            * 张鑫旭
            * [CSS 布局](http://zh.learnlayout.com/)
            * [学习资源集合](http://caibaojian.com/css1)
            * [6个学习网站](https://www.qianduan.net/6-months-worth-of-learning-resources-collection-of-css-websites/)
            * [The Best Way to Learn CSS](https://webdesign.tutsplus.com/tutorials/the-best-way-to-learn-css--webdesign-11906)

    ??? note "JavaScript"

        * 1.1
            * [阮一峰的 JS 教程](https://wangdoc.com/javascript/) (JS入门)
            * [阮一峰的 ES6 教程](https://es6.ruanyifeng.com/)
            * [现代 JavaScript 教程](https://zh.javascript.info/)

        * 1.2
            * MDN
            * 菜鸟教程
            * [JS 秘密花园](http://bonsaiden.github.io/JavaScript-Garden/zh/)
            * [学习指南](https://hijiangtao.github.io/2018/01/25/learn-plain-javascript-from-top-tutorials-for-the-past-year-v-2018/)
            * [ES6 新特性列表](https://fangyinghang.com/es-6-tutorials/)
            * [博客-haha](https://www.cnblogs.com/hahazexia/p/9446585.html)

        * 2
            * 你不知道的 JavaScript (先看上卷，适合进阶)

    ??? note "jQuery / AJAX / JSON"

        ??? info "mdn 定义"

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

        * 1

            * [w3schools](https://www.w3schools.com/jquery/) / [菜鸟](https://www.runoob.com/jquery/jquery-tutorial.html)
            * [jQuery API](https://api.jquery.com/) / [jQuery API 中文文档](https://www.jquery123.com/) / [jQuery 基础](http://jqfundamentals.com/)
            * [廖雪峰](https://www.liaoxuefeng.com/wiki/1022910821149312/1023022609723552)
            * [jQuery 都过时了，那我还学它干嘛？](https://fangyinghang.com/why-still-jquery/)
            * [JSON](https://www.json.org/json-en.html) / [JSON 中文](https://www.json.org/json-zh.html)

        * 2

            * 锋利的 jQuery


??? abstract "笔记内容"

    * Learn

        * 方方课的笔记 ([资料来源：饥人谷](https://jirengu.com/))
        * MDN
        * 书籍总结
        * 项目总结

    * 技能

        * 计算机语言
        * 工具
        * 英语单词

    * 博客记录

