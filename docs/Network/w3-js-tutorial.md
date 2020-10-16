
* [Regular Expressions](https://www.w3schools.com/js/js_regexp.asp) | [正则表达式 菜鸟](https://www.runoob.com/js/js-regexp.html)

??? abstract "[JSON 1](https://www.w3schools.com/js/js_json.asp), [JSON 2](https://www.w3schools.com/JSREF/jsref_obj_json.asp) | [菜鸟](https://www.runoob.com/js/js-json.html)"

    * JSON names require double quotes. JavaScript names do not.
    * [JSON tutorial](https://www.w3schools.com/js/js_json_intro.asp) | [JSON 教程](https://www.runoob.com/json/json-tutorial.html)

    * parse(): 如果不符合 JSON 语法，则直接抛出一个 Error 对象，一般用 try catch 捕获错误
    * stringify(): 由于 JS 的数据类型比 JSON 多，所以不一定能成功。如果失败，则抛出一个 Error 对象。

    ??? note "In JSON, values must be one of the following data types:"

        1. a string: 只支持双引号，不支持单引号和无引号
        * a number: 支持科学计数法
        * an object (containing valid JSON values)
        * an array
        * a boolean
        * null

        不支持函数，不支持变量（所以也不支持引用）


