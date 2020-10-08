
* [菜鸟](https://www.runoob.com/js/js-function-closures.html) | [w3](https://www.w3schools.com/js/js_function_closures.asp) | [w3c](https://www.w3school.com.cn/js/js_function_closures.asp)


## 闭包 Closures

A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). 也就是说，闭包可以让你从内部函数访问外部函数作用域。In JavaScript, closures are created every time a function is created, at function creation time.

??? note "Lexical scoping (词法作用域)"

    ``` javascript
    function init() {
        var name = "Mozilla"; // name 是一个被 init 创建的局部变量 (local variable)
        function displayName() { // displayName() 是内部函数，一个闭包
            alert(name); // 使用了父函数中声明的变量
        }
        displayName();
    }
    init();
    ```

    This is an example of lexical scoping, which describes how a parser (语法分析器) resolves variable names when functions are nested. The word lexical refers to the fact that lexical scoping uses the location where a variable is declared within the source code to determine where that variable is available. Nested functions have access to variables declared in their outer scope.


??? note "Closure"

    ``` javascript
    // 效果同上
    function makeFunc() {
      var name = 'Mozilla';
      function displayName() {
        alert(name);
      }
      return displayName;
    }

    var myFunc = makeFunc();
    myFunc();
    ```

    A closure is the combination of a function and the lexical environment within which that function was declared. This environment 包含了这个闭包创建时作用域内的任何局部变量。In this case, myFunc is a reference to the instance of the function displayName that is created when makeFunc is run. The instance of displayName maintains a reference to its lexical environment, within which the variable name exists. 所以 变量 name 仍然可用.

    ``` javascript
    function makeAdder(x) {
      return function(y) {
        return x + y;
      };
    }

    var add5 = makeAdder(5);
    var add10 = makeAdder(10);

    console.log(add5(2));  // 7
    console.log(add10(2)); // 12
    ```

    In essence(本质上), makeAdder is a function factory. It creates functions that can add a specific value to their argument. In the above example, the function factory creates two new functions—one that adds five to its argument, and one that adds 10.

    add5 and add10 are both closures. They share the same function body definition, but store different lexical environments. In add5's lexical environment, x is 5, while in the lexical environment for add10, x is 10.


??? note "Practical closures"

    闭包很有用，因为它允许你将数据（the lexical environment）与操作数据的函数关联起来。这显然类似于面向对象编程。在面向对象编程中，对象允许你将数据（对象的属性 properties）与一个或者多个方法相关联。

    因此，通常你使用只有一个方法的对象的地方，都可以使用闭包。在 web 中很常见，大部分前端 JavaScript 代码 是 event-based。You define some behavior, and then attach it to an event that is triggered by the user (such as a click or a keypress). The code is attached as a callback (a single function that is executed in response to the event).

??? note "用闭包模拟私有方法"

    Private methods aren't just useful for restricting access to code. They also provide a powerful way of managing your global namespace.

    ??? success "如何用闭包定义 public functions that can access private functions and variables. Note that these closures follow the Module Design Pattern."

        ``` javascript
        var counter = (function() {
          var privateCounter = 0;
          function changeBy(val) {
            privateCounter += val;
          }

          return {
            increment: function() {
              changeBy(1);
            },

            decrement: function() {
              changeBy(-1);
            },

            value: function() {
              return privateCounter;
            }
          };
        })();

        console.log(counter.value());  // 0.

        counter.increment();
        counter.increment();
        console.log(counter.value());  // 2.

        counter.decrement();
        console.log(counter.value());  // 1.
        ```

        三个函数共享一个 lexical environment

        You can't access either of these private members from outside the anonymous function. Instead, you can access them using the three public functions that are returned from the anonymous wrapper.

        Those three public functions are closures that share the same lexical environment.

        ``` javascript
        //You could store this function in a separate variable makeCounter, and then use it to create several counters.
        var makeCounter = function() {
          var privateCounter = 0;
          function changeBy(val) {
            privateCounter += val;
          }
          return {
            increment: function() {
              changeBy(1);
            },

            decrement: function() {
              changeBy(-1);
            },

            value: function() {
              return privateCounter;
            }
          }
        };

        var counter1 = makeCounter();
        var counter2 = makeCounter();

        alert(counter1.value());  // 0.

        counter1.increment();
        counter1.increment();
        alert(counter1.value()); // 2.

        counter1.decrement();
        alert(counter1.value()); // 1.
        alert(counter2.value()); // 0.
        ```

        Using closures in this way provides benefits that are normally associated with object-oriented programming. In particular, data hiding and encapsulation (数据隐藏和封装) .


...


