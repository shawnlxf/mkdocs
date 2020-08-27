
## 1 条件 (conditional structures)

??? note "if...else 语句 (statements)"

        ``` javascript
        // 错误
        // 条件始终为 true 因为 7 (或任何其他非零值) 始终为 true
        if (x === 5 || 7 || 10 || 20) {
          // run my code
        }
        ```

        ``` javascript
        // 正确
        if (x === 5 || x === 7 || x === 10 ||x === 20) {
          // run my code
        }
        ```

??? note "switch 语句 (statements) 伪代码 (pseudocode)"

    ```
    switch (expression) {
      case choice1:
        run this code
        break;

      case choice2:
        run this code instead
        break;

      // include as many cases as you like

      default:
        actually, just run this code
    }
    ```

??? note "三元运算符 伪代码"

    ```
    ( condition ) ? run this code : run this code instead
    ```

    三元运算符不仅仅用于设置变量值；你还可以运行函数或代码行 - 任何你喜欢的东西。


## 2 循环结构 (loop structures)

??? note "for loop / while / do...while"

    ```
    for (initializer; condition; final-expression) {
      // code to run
    }
    ```

    * break / continue

    ```
    initializer
    while (condition) {
      // code to run

      final-expression
    }
    ```

    ```
    initializer
    do {
      // code to run

      final-expression
    } while (condition)
    ```

* [Loops and iteration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration)
* see also


## 3 Functions — reusable blocks of code

请记住，某些内置 (built-in) 的浏览器函数不是 核心 (core) JavaScript 语言的一部分 - 某些被定义为浏览器 API 的一部分，这些 API 建立在默认语言的基础上，以提供更多功能）。

??? note "Functions versus methods"

    程序员把函数称为对象方法（method）的一部分。

    到目前为止，我们使用的内置代码有两种形式：函数和方法。[built-in objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects)


??? note "匿名函数"

    * 通常，你将匿名函数与事件处理程序 (event handler) 一起使用
    * 你还可以将匿名函数分配为变量的值






