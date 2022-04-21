
* [Document Object](https://www.w3schools.com/JSREF/dom_obj_document.asp) | [菜鸟](https://www.runoob.com/jsref/dom-obj-document.html)

    ??? note "The HTMLCollection (NodeList) object represents a collection of nodes. The nodes can be accessed by index numbers. The index starts at 0."

        Tip: You can use the length property of the HTMLCollection object to determine the number of elements with a specified class name, then you can loop through all elements and extract the info you want.


* [Element Object](https://www.w3schools.com/JSREF/dom_obj_all.asp) | [菜鸟](https://www.runoob.com/jsref/dom-obj-all.html)

    ??? note "[nodeType](https://www.w3schools.com/JSREF/prop_node_nodetype.asp)"

        * 1: Element
        * 2: Attr
        * 3: Text
        * 8: Comment

    ??? note "childNodes, children 的不同"

        * childNodes: returns a collection of a node's child nodes, as a NodeList object.
        * children: return a collection of a node's element nodes (excluding text and comment nodes)


    ??? note "innerText, innerHTML and textContent 之间的一些不同，[例子](https://www.w3schools.com/JSREF/tryit.asp?filename=tryjsref_node_textcontent_innerhtml_innertext)"

        * The innerText property returns just the text, without spacing and inner element tags.
        * The innerHTML property returns the text, including all spacing and inner element tags.
        * The textContent property returns the text with spacing, but without inner element tags.

    ??? note "innerText and textContent 之间的一些不同，[例子](https://www.w3schools.com/JSREF/tryit.asp?filename=tryjsref_node_textcontent_innertext)"

        * textContent returns the text content of all elements, while innerText returns the content of all elements, except for `<script>` and `<style>` elements.
        * innerText will not return the text of elements that are hidden with CSS (textContent will).

    * [DOM Style Object](https://www.w3schools.com/JSREF/dom_obj_style.asp)


* [Events](https://www.w3schools.com/JSREF/dom_obj_event.asp) | [菜鸟](https://www.runoob.com/jsref/dom-obj-event.html)
* [HTMLCollection Object](https://www.w3schools.com/JSREF/dom_obj_htmlcollection.asp) | [菜鸟](https://www.runoob.com/jsref/dom-htmlcollection.html)
* [Window Object](https://www.w3schools.com/jsref/obj_window.asp) | [菜鸟](https://www.runoob.com/jsref/obj-window.html)


