
## [JSON (JavaScript Object Notation)](https://www.w3schools.com/JSREF/jsref_obj_json.asp)

??? info

    JSON is a format for storing and transporting data.

    JSON is text, and text can be transported anywhere, and read by any programming language.

    JavaScript Objects 可以转换为 JSON, and JSON 可以转换回 JavaScript Objects.

    This way we can work with the data as JavaScript objects, with no complicated parsing or translations.

??? note "parse()"

    The JSON.parse() method parses a string and returns a JavaScript object.

    The string has to be written in JSON format.

    The JSON.parse() method can optionally transform the result with a function.

    语法：JSON.parse(string, function)

    返回值:	A JSON Object, or Array

    如果不符合 JSON 语法，则直接抛出一个 Error 对象，一般用 try catch 捕获错误


??? note "stringify()"

    The JSON.stringify() method 把 JavaScript objects 转换为 strings.

    When sending data to a web server the data has to be a string.

    ??? info "语法：JSON.stringify(obj, replacer, space)"

        * replacer: 可选。用于变换结果的函数或数组。
        * space: Optional. Either a String or a Number.

    返回值:	A String

    由于 JS 的数据类型比 JSON 多，所以不一定能成功。如果失败，则抛出一个 Error 对象。


??? note "Valid Data Types"

    In JSON, values must be one of the following data types:

    1. a string: 只支持双引号，不支持单引号和无引号
    * a number: 支持科学计数法
    * an object (containing valid JSON values)
    * an array
    * a boolean
    * null

    不支持函数，不支持变量（所以也不支持引用）


