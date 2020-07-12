# HTML

## HTML 入门

...

## 1) Getting started with HTML

* Block versus inline elements（块级元素和内联元素）

    元素分两种类别：

    * Block-level elements

        > form a visible block on a page (块的形式展现)
        >
        > 前后都换行 (new line)
        >
        > 块级元素不会被嵌套进内联元素中，但可以嵌套在其它块级元素中。

    * Inline elements

        > 在块级元素中


* Attributes

    * <a>: 

        * href: web address
        * title: extra information about the link

            > such as a description of the page
            >
            > a tooltip when a cursor hovers

        * target: the browsing context used to display the link

            > target="_blank" will display the link in a new tab

    * Boolean attributes (布尔属性)

        > 他们只能有跟它的属性名一样的属性值

            <input type="text" disabled="disabled">
            <input type="text" disabled>

* Entity references(实体引用): Including special characters in HTML

    > <, >,",' and & are special characters. 
    >
    >They are parts of the HTML syntax itself (HTML语法自身的一部分)
    >
    > & ;

    * <: lt
    * \>: gt
    * ": quot
    * ': apos
    * &: amp

      
      
What’s in the head? Metadata in HTML
  * the head's job is to contain metadata about the document
Adding a title
  * <h1>:  the title of your page content
  * <title>: metadata that represents the title of the overall HTML document (not the document's content.)
Metadata: the <meta> element
  * Metadata is data that describes data
Adding an author and description
  * name, content

