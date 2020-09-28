
## [JavaScript String](https://www.w3schools.com/jsref/jsref_obj_string.asp)

??? info 

    Primitive values, like "John Doe", cannot have properties or methods (because they are not objects).

    But with JavaScript, methods and properties are also available to primitive values, because JavaScript treats primitive values as objects when executing methods and properties.

    All string methods return a new value. They do not change the original variable.

??? note "trim()"

    The trim() method removes whitespace from both sides of a string.

    ??? info 

        The trim() method does not change the original string.

    语法：string.trim()

    返回值:	A String, representing the string with removed whitespace from both ends

??? note "indexOf()"

    indexOf() 方法返回一个指定值在字符串中首次出现的位置。

    如果没有找到匹配的字符串则返回 -1。

    ??? info

        注意：indexOf() 方法区分大小写。

        Tip：查看类似方法 lastIndexOf() 。

    ??? note "语法：string.indexOf(searchvalue, start)"

        start: Optional. Default 0. 规定在字符串中开始检索的位置。

    返回值:	A Number, representing 查找指定字符串第一次出现的位置，如果没找到匹配的字符串则返回 -1。

??? note "replace()"

    全局替换 (global replacement): /blue/g

    全局替换, 忽略大小写 (global, case-insensitive replacement): /blue/gi

    此方法不改变 the original string.

    ??? note "语法：string.replace(searchvalue, newvalue)"

        searchvalue: 也可以是正则表达式

    返回值:	A new String, where the specified value(s) has been replaced by the new value


??? note "toString()"

    返回 a String object 的值.

    返回值:	A String, representing the value of a string

    语法：string.toString()


* length, slice, toLowerCase / toUpperCase, replace
* split

