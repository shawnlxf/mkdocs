
[Howto](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto)

## 1 [HTML 简介](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML)

### 1.1 开始

HTML中的Tags(标签)大小写不敏感，最好都小写

??? note "块级元素和内联元素"

    两种重要的元素类别：

    * 块级元素(Block-level elements)

        > 一个块级元素不会嵌套在一个内联元素内，但是可能会嵌套在另一个块级元素内。

    * 内联元素(Inline elements)

        > 包含在块级元素内，并且仅包围文档内容的一小部分。

??? abstract "Attributes(属性)"

    ??? note "<a\>"

        * href: 指定链接的网址 
        * title: 指定有关链接的其他信息

            > 当光标悬停在元素上时，这将显示为工具提示。

        * target: 指定用于显示链接的浏览上下文 (browsing context)

            > `target="_blank"`: 在新标签页中显示链接

    ??? note "布尔属性"

        > 有时您会看到没有值的属性。这是完全可以接受的。这些称为布尔属性。
        > 
        > 布尔属性只能有一个值，该值通常与属性名相同。

        ``` html
        <input type="text" disabled="disabled">
        ```

        简写：

        ``` html
        <input type="text" disabled>
        ```

??? note "实体引用： 在HTML中包含特殊字符"

    > HTML语法本身的一部分

    | Literal character | Character reference equivalent |
    | ----------------- | ------------------------------ |
    | <                 | `&lt;`                         |
    | >                 | `&gt;`                         |
    | "                 | `&quot;`                       |
    | '                 | `&apos;`                       |
    | &                 | `&amp;`                        |


### 1.2 head

??? note "它包含以下信息:"

    * 页面 <title\>
    * 指向 CSS 的链接
    * 指向自定义 favicon 的链接
    * 其他 metadata（有关HTML的数据，例如作者，以及描述文档的重要关键字） 。）

??? note "最简"

    ``` html
    <!DOCTYPE html>
    <html>
      <head>
        <meta charset="utf-8">
        <title>My test page</title>
      </head>
      <body>
        <p>This is my page</p>
      </body>
    </html>
    ```

head 的工作是包含关于文档的 metadata

??? note "(MDN)metadata: 描述数据的数据"

    * 指定文档的字符编码
    * 添加作者和描述

        * name: 指定 meta 元素的类型
        * content: meta content

            > 描述(含有关键字): 搜索排名靠前(SEO)

??? note "将CSS和JavaScript应用于HTML"

    link 放 head 里

    ``` html
    <link rel="stylesheet" href="my-css-file.css"> 
    ```

    > defer: 基本上指示浏览器加载 HTML 的同时加载 JavaScript
    >
    > 确保在运行 JavaScript 之前已全部加载 HTML

    ``` html
    <script src="my-js-file.js" defer></script>
    ```

### 1.3 text

??? note "Emphasis and importance"

    * Emphasis

        > stress(强调) words by putting them in italics.
        >
        > <i\>: italics

    * Strong importance

        > To emphasize important words, 我们倾向于在口头语言重读(stress)它们，而用书面语言将它们加粗
        >
        > <b\>: bold


### 1.4 hyperlinks (超链接)

??? note "块级链接"

    几乎可以将任何内容转化成链接，甚至块级元素。
    
    !!! success "img"

        ``` html
        <a href="https://www.mozilla.org/en-US/">
        <img src="mozilla-image.png" alt="mozilla logo that links to the mozilla homepage">
        </a>
        ```

??? abstract "URLs and paths"

    * URL(Uniform Resource Locator)

        > 字符串定义 where something is located on the Web

    * URL 使用路径查找文件

    ??? note "文件片段(Document fragments)"


        ``` html
        <!-- 1. 分配 id attribute 给被链接的元素 -->
        <h2 id="Mailing_address">Mailing address</h2>
        ```

        ``` html
        <!-- 2. 在URL的末尾加 #id -->
        <p>Want to write us a letter? Use our <a href="contacts.html#Mailing_address">mailing address</a>.</p>
        ```

        ``` html
        <!-- 或 同一文档的另一部分 -->
        <p>The <a href="#Mailing_address">company mailing address</a> can be found at the bottom of this page.</p>
        ```

    ??? note "在链接到同一网站内的其他位置时，应尽可能使用相对链接"

        1. 读代码更加容易
        2. 浏览器效率降低

??? success "链接到非HTML资源-留下清晰的路标"

    ``` html
    <p><a href="http://www.example.com/large-report.pdf">
        下载销售报告（PDF, 10MB）
    </a></p>

    <p><a href="http://www.example.com/video-stream/">
        观看视频（将在新标签页中播放, HD画质）
    </a></p>

    <p><a href="http://www.example.com/car-game">
        进入汽车游戏（需要Flash插件）
    </a></p>
    ```

??? download "链接到下载时使用 download 属性"

    > 使用 download 属性提供默认的保存文件名

    ``` html
    <a href="https://download.mozilla.org/?product=firefox-latest-ssl&os=win64&lang=en-US"
       download="firefox-latest-64bit-installer.exe">
      Download Latest Firefox for Windows (64-bit) (English, US)
    </a>
    ```

??? note "标准的 URL 查询表示法"

    使用问号（?）将主URL与字段值 (field values) 分开，并使用 & 号将 `mailto:` URL中的每个字段分开。
    
    这是标准的URL查询表示法 (URL query notation)。

### 1.5 进阶 text formatting

### 1.6 文件 和 网站 结构

> 定义网站区域的块级元素 (例如："the header 标题", "the navigation menu 导航菜单", "the main content column 主内容列").

* 文档的基本组成部分

    > 类似的标准组件:

    ??? note "1. header: 页眉"

        > <header\>: 代表一组介绍性内容。

        * 如果它是 <body\> 的子元素，则定义网页的全局 header
        * 如果它是 <article\> 或 <section\> 的子元素，定义那个 section 的 特定的 header

    ??? note "2. navigation bar: 导航栏"

        > <nav\>

        包含页面的主要导航功能。其中不应包含二级链接(Secondary links)等内容。

    ??? abstract "3. main content: 主内容"

        > <main\>，和不同内容的 subsections，用以下元素表示：<article\>, <section\>, 和 <div\>

        !!! note "<main\>: 存放每个页面独有的内容，每个页面上只能用一次"
        !!! note "<article\>: 包围的内容即一篇文章，比如一篇博客"
        ??? note "<section\>: "

            * 更适用于组织页面使其按功能（比如迷你地图、一组文章标题和摘要）分块。
            * 最好以 标题(heading) 开头

    ??? abstract "4. sidebar: 侧边栏"

        > <aside\>: 经常放在 <main\> 里

        提供与主要内容间接相关的其他信息（词汇表条目，作者传记，相关链接等）(glossary entries, author biography, related links, etc.)。

    ??? note "5. footer: 页脚"

        > <footer\>: 页面的一组结束内容

??? note "无语义元素 (Non-semantic wrappers)"

    * span
    * div: 只有在没有更好的语义方案时才选择它，而且要尽可能少用，否则文档的升级和维护工作会非常困难。

??? note "换行和水平分割线 (Line breaks and horizontal rules)"

    1. <br\>

        * 在段落中创建换行; 
        * 这是在需要一系列固定短线的情况下（例如在邮寄地址或一首诗中）施加刚性结构的唯一方法。

    2. <hr\>

        * 在文档中创建一个水平规则，该水平规则表示文本的主题变化（例如主题或场景的改变）。在视觉上，它看起来像一条水平线。

### 1.7 Debugging HTML

??? note "解析 HTML"

    * 浏览器并不会将 HTML 编译成其它形式，而是直接解析并显示结果（称之为解释(interpreted)，而非编译(compiled)）
    * 浏览器解析 HTML 的方式比运行编程语言的方式要宽容(permissive)得多，这既是好事也是坏事。

!!! note "错误"

    * 语法错误
    * 逻辑错误



## 2 [多媒体 和 嵌入](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding)



## 3 [HTML 表格](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables)