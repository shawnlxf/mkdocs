
# [JavaScript reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)

??? info "[Callback function (回调函数)](https://developer.mozilla.org/en-US/docs/Glossary/Callback_function)"

    回调函数是作为参数 (argument) 传递给另一个函数的函数，然后在外部函数内被调用以完成某种例程 (routine) 或操作 (action) 。

    ``` javascript
    function greeting(name) {
      alert('Hello ' + name);
    }

    function processUserInput(callback) {
      var name = prompt('Please enter your name.');
      callback(name);
    }

    processUserInput(greeting);
    ```

    上面的示例是一个同步回调(synchronous callback)，因为它立即执行。

    但是请注意，回调通常用于在异步操作 (asynchronous operation) 完成之后继续执行代码 - 这些称为异步回调 (asynchronous callbacks) 。

    A good example is the callback functions executed inside a [.then()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then) block chained onto the end of a promise after that promise fulfills or rejects. This structure is used in many modern web APIs, such as [fetch()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch).


??? note "[Classes (类)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)"

??? note "[Template literals (Template strings，模板字符串)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)"

??? note "[Object initializer (对象初始化)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer)"

## Statements

??? note "for...in"

    The for...in statement (语句) iterates (迭代) over all enumerable properties (可枚举属性) of an object that are keyed by strings (ignoring ones keyed by Symbols), including inherited enumerable properties (继承的可枚举属性).

    语法：

    ```
    for (variable in object)
      statement
    ```






## Expressions and operators

### Primary expressions (主要表达式)

??? note "[this](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)"

    与其它语言相比，一个函数的 this 关键字在 JavaScript 中的表现有点不同。在 [strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode) 和 non-strict mode 之间也有一些区别。

    which don't provide their own this binding (it retains the this value of the enclosing lexical context).

    在大多数情况下，this 的值取决于函数的调用方式（运行时绑定, runtime binding）。在执行过程 (execution) 中不能通过赋值来设置它，并且每次调用该函数时可能会有所不同。ES5 introduced the [bind()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind) method to [set the value of a function's this regardless of how it's called](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this#The_bind_method)，ES2015 引入了箭头函数，箭头函数不提供自己的 this 绑定 (it retains the `this` value of the enclosing lexical context)。


??? note "[{} Object initializer/literal syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer)"

### Unary operators (一元运算符)

??? note "typeof"

    The typeof operator (运算符) returns a string indicating the type of the unevaluated operand (操作数) .

    语法：typeof operand
         typeof(operand)


### Relational operators

??? info

    A comparison operator compares its operands and returns a Boolean value based on whether the comparison is true.

??? note "instanceof"

    The instanceof operator tests to see if the prototype property of a constructor appears anywhere in the prototype chain of an object. 返回值是一个布尔值。

    The instanceof operator tests the presence of constructor.prototype in object's prototype chain.

    语法：object instanceof constructor





## Assignment operators

??? note "[Destructuring assignment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)"



## [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions)

??? note "[Arrow function expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)"

