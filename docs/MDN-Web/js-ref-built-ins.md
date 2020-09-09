
## Built-ins

### Fundamental objects (基本对象)

??? abstract "w3schools-JS Functions"

    ??? note "Function Call"

        In a function definition, this refers to the "owner" of the function.


??? abstract "[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)"

    ??? abstract "Static methods"

        ??? note "Object.create()"

            创建一个新对象，使用已经存在的对象作为新创建对象的原型。

            语法：Object.create(proto, [propertiesObject])

        ??? note "Object.assign()"

            Object.assign() 方法用于将所有 enumerable own properties (可枚举属性) 的值从一个或多个源对象复制到目标对象。它将返回目标对象。

            语法：Object.assign(target, ...sources)





??? abstract "[Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function)"

    Every JavaScript function is actually a Function object. This can be seen with the code (function(){}).constructor === Function, which returns true.

    ??? abstract "Instance methods"

        ??? note "`Function.prototype.call()`"

            语法：func.call([thisArg[, arg1, arg2, ...argN]])

            `call()` 允许为一个对象分配和调用属于一个不同的对象的函数/方法。

            `call()` 提供新的 this 值给函数/方法。使用 `call()`，你可以编写一次方法，然后在另一个对象中继承该方法，而不必为新对象重写该方法。

            examples:

            ??? note "Using call to chain constructors for an object"

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
            

## [W3-Array](https://www.w3schools.com/JSREF/jsref_obj_array.asp)            

> [MDN-Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

??? note "from()"

    The Array.from() method returns an Array object from any object with a length property or an iterable object.

    语法：Array.from(object, mapFunction, thisValue)

    返回值:	An Array object

??? note "filter()"

    The filter() method creates an array filled with all array elements that pass a test (provided as a function).

    ??? tip

        filter() 不会对空数组进行检测。

        filter() 不会改变原始数组。

    语法：array.filter(function(currentValue, index, arr), thisValue)

    返回值:	返回数组，包含了通过测试的所有数组元素。如果没有元素通过测试则返回空数组。





