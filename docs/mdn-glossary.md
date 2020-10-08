
??? quote "World Wide Web"


    The World Wide Web—commonly referred to as WWW, W3, or the Web—is an interconnected system of public webpages accessible through the Internet. The Web is not the same as the Internet: the Web is one of many applications built on top of the Internet.

    "the Web" 由三个组件组成：

    1. HTTP
    2. URL
    3. HTML

??? quote "IIFE"

    An IIFE (Immediately Invoked Function Expression) is a JavaScript function that runs as soon as it is defined.

    ``` javascript
    (function () {
        statements
    })();
    ```

    ??? success "Examples:"

        The function becomes a function expression which is immediately executed. The variable within the expression can not be accessed from outside it.

        ``` javascript
        (function () {
            var aName = "Barry";
        })();
        // Variable aName is not accessible from the outside scope
        aName // throws "Uncaught ReferenceError: aName is not defined"
        ```

        Assigning the IIFE to a variable stores the function's return value, not the function definition itself.

        ``` javascript
        var result = (function () {
            var name = "Barry"; 
            return name; 
        })(); 
        // Immediately creates the output: 
        result; // "Barry"
        ```



