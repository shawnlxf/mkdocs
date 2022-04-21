
## Built-ins

### Fundamental objects (基本对象)

??? abstract "w3schools-JS Functions"

    ??? note "Function Call"

        In a function definition, this refers to the "owner" of the function.


#### [Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)

??? abstract "Static methods"

    ??? note "Object.create()"

        创建一个新对象，使用已经存在的对象作为新创建对象的原型。

        语法：Object.create(proto, [propertiesObject])

    ??? note "Object.assign()"

        Object.assign() 方法用于将所有 enumerable own properties (可枚举属性) 的值从一个或多个源对象复制到目标对象。它将返回目标对象。

        语法：Object.assign(target, ...sources)


#### [Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function)

??? quote "每个 JavaScript 函数实际上都是一个 Function 对象"

    ``` javascript
    (function(){}).constructor === Function // true
    ```

??? abstract "Instance methods"

    ??? note "Function.prototype.call()"

        语法：func.call([thisArg[, arg1, arg2, ...argN]])

        `call()` 允许为不同的对象分配和调用属于一个对象的函数/方法。

        `call()` 提供新的 this 值给函数/方法。使用 `call()`，你可以编写一次方法，然后在另一个对象中继承该方法，而不必为新对象重写该方法。

        ??? note "与 apply() 的不同"
        
            While the syntax of this function is almost identical to that of apply(), the fundamental difference is that call() accepts an argument list, while apply() accepts a single array of arguments.

        Examples:

        ??? success "Using call to chain constructors for an object (similar to Java)"

            ``` javascript
            function Product(name, price) {
              this.name = name;
              this.price = price;
            }

            function Food(name, price) {
              Product.call(this, name, price);
              this.category = 'food';
            }

            function Toy(name, price) {
              Product.call(this, name, price);
              this.category = 'toy';
            }

            const cheese = new Food('feta', 5);
            const fun = new Toy('robot', 40);
            ```
        
        ??? success "Using call to invoke an anonymous function"

            Passing the object as this value is not strictly necessary, but is done for explanatory purpose (解释目的).

            ``` javascript
            // add a print function to every object, which is able 
            //to print the correct index of the object in the array.
            const animals = [
              { species: 'Lion', name: 'King' },
              { species: 'Whale', name: 'Fail' }
            ];

            for (let i = 0; i < animals.length; i++) {
              (function(i) {
                this.print = function() {
                  console.log('#' + i + ' ' + this.species
                              + ': ' + this.name);
                }
                this.print();
              }).call(animals[i], i);
            }
            ```

        ??? success "Using call to invoke a function and specifying the context for 'this'"

            when we call greet, the value of this will be bound to object obj.

            ``` javascript
            function greet() {
              const reply = [this.animal, 'typically sleep between', this.sleepDuration].join(' ');
              console.log(reply);
            }

            const obj = {
              animal: 'cats', sleepDuration: '12 and 16 hours'
            };

            greet.call(obj);  // cats typically sleep between 12 and 16 hours
            ```

        ??? success "Using call to invoke a function and without specifying the first argument"

            If the first argument is not passed, the value of `this` is bound to the global object.

            ``` javascript
            var sData = 'Wisen';

            function display() {
              console.log('sData value is %s ', this.sData);
            }

            display.call();  // sData value is Wisen
            ```

            ``` javascript
            // In strict mode, the value of this will be undefined.
            'use strict';

            var sData = 'Wisen';

            function display() {
              console.log('sData value is %s ', this.sData);
            }

            display.call(); // Cannot read the property of 'sData' of undefined
            ```

    ??? note "Function.prototype.bind()"

        bind() 方法创建一个新函数，该新函数在被调用时将其 this 关键字设置为所提供的值，并在调用新函数时提供给定的参数序列。

        语法：let boundFunc = func.bind(thisArg[, arg1[, arg2[, ...argN]]])

        Examples:

        ??? success "Creating a bound function"

            ``` javascript
            this.x = 9;    // 'this' refers to global 'window' object here in a browser
            const module = {
              x: 81,
              getX: function() { return this.x; }
            };

            module.getX();
            //  returns 81

            const retrieveX = module.getX;
            retrieveX();
            //  returns 9; the function gets invoked at the global scope

            //  Create a new function with 'this' bound to module
            //  New programmers might confuse the
            //  global variable 'x' with module's property 'x'
            const boundGetX = retrieveX.bind(module);
            boundGetX(); 
            //  returns 81
            ```

        ??? success "Partially applied functions"

            make a function with pre-specified initial arguments(使函数具有预先指定的初始参数).

            ``` javascript
            function list() {
              return Array.prototype.slice.call(arguments);
            }

            function addArguments(arg1, arg2) {
              return arg1 + arg2
            }

            const list1 = list(1, 2, 3);
            //  [1, 2, 3]

            const result1 = addArguments(1, 2);
            //  3

            // Create a function with a preset leading argument
            const leadingThirtysevenList = list.bind(null, 37);

            // Create a function with a preset first argument.
            const addThirtySeven = addArguments.bind(null, 37); 

            const list2 = leadingThirtysevenList(); 
            //  [37]

            const list3 = leadingThirtysevenList(1, 2, 3); 
            //  [37, 1, 2, 3]

            const result2 = addThirtySeven(5); 
            //  37 + 5 = 42 

            const result3 = addThirtySeven(5, 10);
            //  37 + 5 = 42 
            //  (the second argument is ignored)
            ```

    ??? note "Function.prototype.apply()"

        arguments provided as an array (or an array-like object).        

        语法：func.apply(thisArg, [ argsArray])

        Examples:

        ??? success "Using apply to append (追加) an array to another"

            concat does have the desired behaviour in this case, but it does not append to the existing array—it instead creates and returns a new array.

            ``` javascript
            const array = ['a', 'b'];
            const elements = [0, 1, 2];
            array.push.apply(array, elements);
            console.info(array); // ["a", "b", 0, 1, 2]
            ```

        ??? success "Using apply and built-in functions"

            ``` javascript
            // min/max number in an array
            const numbers = [5, 6, 2, 3, 7];

            // using Math.min/Math.max apply
            let max = Math.max.apply(null, numbers); 
            // This about equal to Math.max(numbers[0], ...)
            // or Math.max(5, 6, ...)

            let min = Math.min.apply(null, numbers);

            // vs. simple loop based algorithm
            max = -Infinity, min = +Infinity;

            for (let i = 0; i < numbers.length; i++) {
              if (numbers[i] > max) {
                max = numbers[i];
              }
              if (numbers[i] < min) {
                min = numbers[i];
              }
            }
            ```

            The JavaScriptCore engine has hard-coded argument limit of 65536.

        ??? success "Using apply to chain constructors (similar to Java)"

            ``` javascript
            // create a global Function method called construct
            // 相对较新，还有其他方法
            Function.prototype.construct = function(aArgs) {
              let oNew = Object.create(this.prototype);
              this.apply(oNew, aArgs);
              return oNew;
            };
            ```






