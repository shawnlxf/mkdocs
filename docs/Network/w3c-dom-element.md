
## [Element Object](https://www.w3schools.com/JSREF/dom_obj_all.asp)

* [nodeType](https://www.w3schools.com/jsref/prop_node_nodetype.asp)
* classList

??? info

    In the HTML DOM, the Element object represents an HTML element, like P, DIV, A, TABLE, or any other HTML element.

??? note "insertBefore()"

    The insertBefore() method inserts a node as a child, right before an existing child, which you specify.

    ??? tip

        If you want to create a new list item, with text, remember to create the text as a Text node which you append to the `<li>` element, then insert `<li>` to the list.

    You can also use the insertBefore method to insert/move an existing element.

    语法：node.insertBefore(newnode, existingnode)

    返回值:	A Node Object, representing the inserted node


??? note "appendChild()"

    The appendChild() method appends a node as the last child of a node.

    ??? tip

        If you want to create a new paragraph, with text, remember to create the text as a Text node which you append to the paragraph, then append the paragraph to the document.

    You can also use this method to move an element from one element to another.

    ??? tip

        Use the insertBefore() method to insert a new child node before a specified, existing, child node.

    语法：node.appendChild(node)

    返回值:	A Node Object, representing the appended node


??? note "removeChild()"

    The removeChild() method removes a specified child node of the specified element.

    Returns the removed node as a Node object, or null if the node does not exist.

    ??? tip

        The removed child node is no longer part of the DOM. However, with the reference returned by this method, it is possible to insert the removed child to an element at a later time.

        Use the appendChild() or insertBefore() method to insert the removed node into the same document. To insert it to another document, use the document.adoptNode() or document.importNode() method.

    语法：node.removeChild(node)

    返回值:	A Node object, representing the removed node, or null if the node does not exist


??? note "firstChild"

    !!! note "Whitespace inside elements is considered as text, and text is considered as nodes"

    ??? tip

        Use the element.childNodes property to return any child node of a specified node. childNodes[0] will produce the same result as firstChild.

        To return the last child node of a specified node, use the lastChild property.
    
    语法：node.firstChild

    返回值:	A Node object, representing the first child of a node, or null if there are no child nodes

??? note "children"

    children 属性返回元素的子元素的集合，是一个 HTMLCollection 对象。

    The elements in the collection are sorted as they appear in the source code and can be accessed by index numbers. The index starts at 0.

    ??? tip

        你可以使用 HTMLCollection 对象的 length property 确定子元素的数量，然后你可以遍历所有 children，从而获取你想要的信息。

    ??? note "children 属性与 childNodes 属性的差别"

        * childNodes contain all nodes, including text nodes and comment nodes
        * children only contain element nodes.

    返回值:	A live HTMLCollection object, 表示元素节点的一个集合. The elements in the returned collection are sorted as they appear in the source code



??? note "getAttribute()"

    返回值:	A String, representing the specified attribute's value.

    ??? info

        If the attribute does not exist, the return value is null or an empty string ("")

??? note "setAttribute()"

    ``` javascript
    // Bad
    element.setAttribute("style", "background-color: red;");
    ```

    ``` javascript
    // Good
    // because this will not overwrite other CSS properties that may be specified in the style attribute
    element.style.backgroundColor = "red";
    ```

    语法：element.setAttribute(attributename, attributevalue)

??? note "innerText"

    The innerText property sets or returns the text content of the specified node, and all its descendants.

    If you set the innerText property, any child nodes are removed and replaced by a single Text node containing the specified string.

    ??? info

        This property 与 textContent property 相似, 但是有一些不同:

        * textContent returns the text content of all elements, while innerText returns the content of all elements, except for `<script>` and `<style>` elements.

        * innerText will not return the text of elements that are hidden with CSS (textContent will). 

        To set or return the HTML content of an element, use the innerHTML property.

    返回值: A String, representing the "rendered" text content of a node and all its descendants

??? note "textContent"

    ??? tip

        Sometimes this property can be used instead of the nodeValue property, but remember that this property returns the text of all child nodes as well.

    返回值:	A String, representing the text of the node and all its descendants.
    Returns null if the element is a document, a document type, or a notation.

??? note "innerHTML"

    The innerHTML property sets or returns the HTML content (inner HTML) of an element.

    返回值:	A String, representing the HTML content of an element


??? note "innerText, innerHTML and textContent 之间的一些不同"

    * The innerText property returns just the text, without spacing and inner element tags.
    * The innerHTML property returns the text, including all spacing and inner element tags.
    * The textContent property returns the text with spacing, but without inner element tags.


??? note "[style](https://www.w3schools.com/JSREF/prop_html_style.asp)"

??? note "classList"

    语法: element.classList

    Properties: length

    Methods:

    * add(class1, class2, ...)
    * contains(class)
    * item(index)
    * remove(class1, class2, ...)
    * toggle(class, true|false)

??? note "addEventListener()"

    The addEventListener() method attaches an event handler to the specified element.

    语法：element.addEventListener(event, function, useCapture)

    ??? tip "event"

        Do not use the "on" prefix. For example, use "click" instead of "onclick".

??? note "removeEventListener()"

    The removeEventListener() method removes an event handler that has been attached with the addEventListener() method.

    Note: To remove event handlers, the function specified with the addEventListener() method must be an external function, like in the example above (myFunction).

    Anonymous functions, like "element.removeEventListener("event", function(){ myScript });" will not work.

??? note "nextSibling"

    The returned node is returned as a Node object.

    ??? info

        The difference between this property and nextElementSibling, is that nextSibling returns the next sibling node as an element node, a text node or a comment node, while nextElementSibling returns the next sibling node as an element node (ignores text and comment nodes).

    This property is read-only.

    返回值:	A Node object, representing the next sibling of the node, or null if there is no next sibling

