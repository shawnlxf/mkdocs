
## [Document Object](https://www.w3schools.com/JSREF/dom_obj_document.asp)

??? info

    When an HTML document is loaded into a web browser, it becomes a document object.

    The document object is the root node of the HTML document.

??? note "createElement() 常用"

    ??? tip

        HTML elements often contains text. To create a button with text, use the `innerText` or `innerHTML` properties of the element object

    The createElement() method creates an Element Node with the specified name.

    ??? tip

        After the element is created, use the `#!javascript element.appendChild()` or `#!javascript element.insertBefore()` method to insert it to the document.

    语法：document.createElement(nodename)

    返回值:	An Element object, which represents the created Element node

??? note "querySelectorAll() 常用"

    querySelectorAll() 方法返回文档中匹配指定 CSS selector(s) 的所有元素，as a static NodeList object.

    NodeList 对象表示节点的集合。节点可以通过 index numbers 访问，index 从 0 开始。

    ??? tip

        你可以使用 NodeList 对象的 length property 确定匹配指定 selector 的元素数量，然后你可以遍历所有元素，从而获取你想要的信息。

    语法：document.querySelectorAll(CSS selectors)

    返回值:	一个 NodeList 对象，表示文档中匹配指定 CSS selector(s) 的所有元素。The NodeList is a static collection, meaning that changes in the DOM has NO effect in the collection. Throws a SYNTAX_ERR exception if the selector(s) is invalid


* querySelector() 常用
* addEventListener()
* removeEventListener()

* The HTMLCollection object represents a collection of nodes. The nodes can be accessed by index numbers. The index starts at 0.

??? note "getElementById()"

    返回值:	An Element Object, representing an element with the specified ID. Returns null if no elements with the specified ID exists


??? note "getElementsByClassName()"

    搜索多个 class names，用空格分开，如 "test demo"

    返回值:	An HTMLCollection object, representing a collection of elements with the specified class name. The elements in the returned collection are sorted as they appear in the source code.

??? note "getElementsByTagName()"

    Tip: The parametervalue "*" returns all elements in the document.

    返回值:	An HTMLCollection object, representing a collection of elements with the specified tag name. The elements in the returned collection are sorted as they appear in the source code.








