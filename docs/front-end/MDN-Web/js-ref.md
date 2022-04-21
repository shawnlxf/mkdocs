
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

??? abstract "[Template literals (Template strings，模板字符串)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)"

    Template literals are string literals allowing embedded expressions (允许嵌入表达式). 你可以使用多行字符串和字符串插值特性。

    语法：

    ```
    `string text`

    // 多行字符串
    `string text line 1
     string text line 2`

    // Expression interpolation (表达式插值)
    `string text ${expression} string text`

    tag`string text ${expression} string text`
    ```

    模板字面量 可以包含 placeholders (占位符, ${expression})。占位符中的表达式 和 backticks (反引号，\` \`) 之间的文本 被传递给一个函数。

    默认函数只是将部分 (the parts) 连接到一个字符串中。如果模板字面量前面有一个表达式(这里是 tag)，这被称为标记模板 (tagged template)。In that case, the tag expression (usually a function) gets called with the template literal, which you can then manipulate before outputting.

    ??? note "表达式插值"

        ``` javascript
        let a = 5;
        let b = 10;
        console.log('Fifteen is ' + (a + b) + ' and\nnot ' + (2 * a + b) + '.');
        // "Fifteen is 15 and
        // not 20."
        ```

        Now, with template literals, you are able to make use of the syntactic sugar (语法糖), making substitutions like this more readable:

        ``` javascript
        let a = 5;
        let b = 10;
        console.log(`Fifteen is ${a + b} and
        not ${2 * a + b}.`);
        // "Fifteen is 15 and
        // not 20."
        ```



??? note "[Object initializer (对象初始化)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer)"

## Statements (语句)

??? note "for...in"

    The for...in statement (语句) iterates (迭代) over all enumerable properties (可枚举属性) of an object that are keyed by strings (ignoring ones keyed by Symbols), including inherited enumerable properties (继承的可枚举属性).

    语法：

    ```
    for (variable in object)
      statement
    ```






## Expressions and operators

### Primary expressions (主要表达式)

??? note "[w3 this](https://www.w3schools.com/js/js_this.asp)"

??? note "[MDN this](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)"

    与其它语言相比，一个函数的 this 关键字在 JavaScript 中的表现有点不同。在 [strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode) 和 non-strict mode 之间也有一些区别。

    在大多数情况下，this 的值取决于函数的调用方式（运行时绑定, runtime binding）。在执行过程 (execution) 中不能通过赋值来设置它，并且每次调用该函数时可能会有所不同。ES5 introduced the [bind()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind) method to [set the value of a function's this regardless of how it's called](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this#The_bind_method)，ES2015 引入了箭头函数，箭头函数不提供自己的 this 绑定 (it retains the `this` value of the enclosing lexical context)。

    value: A property of an execution context (global, function or eval) that, in non–strict mode, is always a reference to an object and in strict mode can be any value.

    ??? note "Global context"

        ``` javascript
        // In web browsers, the window object is also the global object:
        console.log(this === window); // true
        
        a = 37;
        console.log(window.a); // 37
        
        this.b = "MDN";
        console.log(window.b)  // "MDN"
        console.log(b)         // "MDN"
        ```

    ??? note "Function context"

        在函数内部，this 的值取决于函数被调用的方式。

        ``` javascript
        function f1() {
          return this;
        }

        // In a browser:
        f1() === window; // true

        // In Node:
        f1() === globalThis; // true
        ```

        ``` javascript
        function f2() {
          'use strict'; // see strict mode
          return this;
        }

        f2() === undefined; // true
        ```

        当调用函数时将 this 值设置为特殊值，使用 call(), 或 apply()

        ``` javascript
        // An object can be passed as the first argument to call or apply and this will be bound to it.
        var obj = {a: 'Custom'};

        // We declare a variable and the variable is assigned to the global window as its property.
        var a = 'Global';

        function whatsThis() {
          return this.a;  // The value of this is dependent on how the function is called
        }

        whatsThis();          // 'Global' as this in the function isn't set, so it defaults to the global/window object
        whatsThis.call(obj);  // 'Custom' as this in the function is set to obj
        whatsThis.apply(obj); // 'Custom' as this in the function is set to obj
        ```

    ??? note "Class context"

        与 functions 类似, since classes are functions under the hood. 但有一些不同。

        Within a class constructor, `this` is a regular object. All non-static methods within the class are added to the prototype of `this`:

        ``` javascript
        class Example {
          constructor() {
            const proto = Object.getPrototypeOf(this);
            console.log(Object.getOwnPropertyNames(proto));
          }
          first(){}
          second(){}
          static third(){}
        }

        new Example(); // ['constructor', 'first', 'second']
        // Note: Static methods are not properties of this. They are properties of the class itself.
        ```

    ??? note "this and object conversion"

        ``` javascript
        function add(c, d) {
          return this.a + this.b + c + d;
        }

        var o = {a: 1, b: 3};

        // The first parameter is the object to use as
        // 'this', subsequent parameters are passed as 
        // arguments in the function call
        add.call(o, 5, 7); // 16

        // The first parameter is the object to use as
        // 'this', the second is an array whose
        // members are used as the arguments in the function call
        add.apply(o, [10, 20]); // 34
        ```

        Note that in non–strict mode, with call and apply, 如果传递给 this 的值不是对象, 则将尝试将其转换为对象. Values null and undefined become the global object. Primitives like 7 or 'foo' will be converted to an Object using the related constructor, so the primitive number 7 is converted to an object as if by new Number(7) and the string 'foo' to an object as if by new String('foo'), e.g.

        ``` javascript
        function bar() {
          console.log(Object.prototype.toString.call(this));
        }

        bar.call(7);     // [object Number]
        bar.call('foo'); // [object String]
        bar.call(undefined); // [object global]
        ```

    ??? note "As an object method"

        When a function is called as a method of an object, its `this` is set to the object the method is called on (调用该方法的对象).

        ``` javascript
        var o = {
          prop: 37,
          f: function() {
            return this.prop;
          }
        };

        console.log(o.f()); // 37
        ```

        ``` javascript
        // This demonstrates that it matters only that 
        // the function was invoked from the f member of o.
        var o = {prop: 37};

        function independent() {
          return this.prop;
        }

        o.f = independent;

        console.log(o.f()); // 37
        ```

        ``` javascript
        // Similarly, the this binding is only affected 
        // by the most immediate member reference.
        o.b = {g: independent, prop: 42};
        console.log(o.b.g()); // 42
        ```


??? note "[{} Object initializer/literal syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer)"

### Left-hand-side expressions

??? note "...obj"

    Spread syntax (..., 展开语法)

    Spread syntax (...) allows an iterable such as an array expression or string to be expanded in places where zero or more arguments (for function calls) or elements (for array literals) are expected, or an object expression to be expanded in places where zero or more key-value pairs (for object literals) are expected.




### Unary operators (一元运算符)

??? note "typeof"

    The typeof operator (运算符) returns a string indicating the type of the unevaluated operand (操作数) .

    语法：typeof operand
         typeof(operand)


### Relational operators (关系运算符)

??? info

    A comparison operator compares its operands and returns a Boolean value based on whether the comparison is true.

??? note "instanceof"

    The instanceof operator tests to see if the prototype property of a constructor appears anywhere in the prototype chain of an object. 返回值是一个布尔值。

    The instanceof operator tests the presence of constructor.prototype in object's prototype chain.

    语法：object instanceof constructor



### Assignment operators (赋值运算符)

??? note "[Destructuring assignment (解构赋值)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)"

    The destructuring assignment syntax is a JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct (不同的) variables.

    assignment 的左边定义 what values to unpack from the sourced variable.

    This capability is similar to features present in languages such as Perl and Python.

    ``` javascript
    // Default values
    // A variable can be assigned a default, in the case that the value unpacked from the array is undefined.
    let a, b;

    [a=5, b=7] = [1];
    console.log(a); // 1
    console.log(b); // 7
    ```

    ``` javascript
    // Swapping variables 交换变量
    // 没有解构赋值的情况下，交换两个变量需要一个临时变量（或者用低级语言中的 XOR-swap 技巧）。
    let a = 1;
    let b = 3;

    [a, b] = [b, a];
    console.log(a); // 3
    console.log(b); // 1

    const arr = [1,2,3];
    [arr[2], arr[1]] = [arr[1], arr[2]];
    console.log(arr); // [1,3,2]
    ```

    ``` javascript
    // 将剩余数组赋值给一个变量
    // 总是作为最后一个元素
    const [a, ...b] = [1, 2, 3];
    console.log(a); // 1
    console.log(b); // [2, 3]
    ```




## [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions)

??? note "[Arrow function expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)"

