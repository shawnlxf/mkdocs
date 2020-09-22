
## [W3-Array](https://www.w3schools.com/JSREF/jsref_obj_array.asp)            

> [MDN-Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

### Array Properties

??? note "constructor"

    返回数组的 constructor function。

    返回值是 a reference to the function, not the name of the function:

    ```
    function Array() { [native code] }
    ```

    你可以使用 constructor property 检查一个变量是否是数组。

??? note "length"

    设置或返回 数组中元素的数量。

??? note "prototype"

    The prototype constructor allows you to add new properties and methods to the Array() object.

    When constructing a property, ALL arrays will be given the property, and its value, as default.

    When constructing a method, ALL arrays will have this method available.

    Note: Array.prototype does not refer to a single array, but to the Array() object itself.

    Note: Prototype is a global object constructor which is available for all JavaScript objects.


### Array Methods

??? note "concat()"

    连接两个或多个数组。

    该方法不会改变现有的数组，但是会返回一个新数组, containing the values of the joined arrays。

    语法：array1.concat(array2, array3, ..., arrayX)

??? note "copyWithin()"

    拷贝数组元素到数组的另一个位置中，overwriting the existing values。

    This method will never add more items to the array.

    Note: this method overwrites the original array.

    ??? info "语法：array.copyWithin(target, start, end)"

        * start: Optional. default is 0
        * end: Optional. default is array.length

    返回值:	An Array, the changed array


??? note "from()"

    The Array.from() method 从拥有 length 属性的对象或可迭代的对象 返回一个数组对象

    ??? info "语法：Array.from(object, mapFunction, thisValue)"

        * mapFunction: optional
        * thisValue: optional

    返回值:	An Array object

??? note "filter()"

    The filter() method creates an array filled with all array elements that pass a test (provided as a function).

    ??? tip

        filter() 不会对空数组进行检测。

        filter() 不会改变原始数组。

    ??? info "语法：array.filter(function(currentValue, index, arr), thisValue)"

        * index: Optional
        * arr: Optional
        * thisValue: Optional. If this parameter is empty, the value "undefined" will be passed as its "this" value

    返回值:	返回数组，包含了通过测试的所有数组元素。如果没有元素通过测试则返回空数组。


??? note "find()"

    返回一个数组中的第一个元素的值 that pass a test (provided as a function).

    The find() method executes the function once for each element present in the array:

    * If it finds an array element where the function returns a true value, find() returns the value of that array element (and does not check the remaining values)
    * Otherwise it returns undefined

    ??? tip

        find() does not execute the function for empty arrays.

        find() 不改变 the original array.

    ??? note "语法：array.find(function(currentValue, index, arr),thisValue)"

        * index: Optional
        * arr: Optional
        * thisValue: Optional. If this parameter is empty, the value "undefined" will be passed as its "this" value

    返回值:	Returns the array element value if any of the elements in the array pass the test, otherwise it returns undefined


??? note "findIndex()"

    返回值:	Returns the array element index if any of the elements in the array pass the test, otherwise it returns -1


!!! note "reverse(): this method 会改变 the original array."

??? note "shift()"

    removes 数组的第一个元素.

    ??? tip

        此方法改变数组的长度！

        The return value of the shift method is the removed item.

        this method 会改变 the original array.

    返回值:	Any type*, representing the removed array item. *An array item can be a string, a number, an array, a boolean, or any other object types that are allowed in an array.


??? note "unshift()"

    向数组的开头添加一个或更多元素，并返回新的长度。

    注意: 此方法改变数组的长度。

    语法：array.unshift(item1, item2, ..., itemX)

    返回值:	A Number, representing 数组的新长度


??? note "pop()"

    removes 数组的最后一个元素并返回删除的元素。

    注意：此方法改变数组的长度！
    
    返回值:	Any type*, representing the removed array item. *An array item can be a string, a number, an array, a boolean, or any other object types that are allowed in an array.


??? note "push()"

    向数组的末尾添加一个或多个元素，并返回新的长度。

    注意：此方法改变数组的长度。

    语法：array.push(item1, item2, ..., itemX)

    返回值:	A Number, representing 数组的新长度

??? note "toString()"

    returns a string with all the array values, separated by commas.

    Note: This method 不会改变 the original array.


??? note "forEach()"

    calls a function once for each element in an array, in order.

    Note: the function is not executed for array elements without values.

    ??? note "语法：array.forEach(function(currentValue, index, arr),thisValue)"

        * index: Optional
        * arr: Optional
        * thisValue: Optional. If this parameter is empty, the value "undefined" will be passed as its "this" value

    返回值: undefined

??? note "indexOf()"

    返回数组中某个指定的元素位置。

    搜索将从指定位置开始，如果开始位置没有指定则从头到尾

    Returns -1 if the item is not found.

    If the item is present more than once, indexOf 方法返回第一次出现的位置。

    Tip: If you want to search from end to start, use the lastIndexOf() method

    ??? info "语法：array.indexOf(item, start)"

        start: Optional. Where to start the search. Negative values will start at the given position counting from the end, and search to the end.

    返回值:	A Number, representing the position of the specified item, otherwise -1

??? note "slice()"

    returns the selected elements in an array, as a new array object.

    The slice() method selects the elements starting at the given start argument, and ends at, but does not include, the given end argument.

    Note: The original array 将不会被改变.

    ??? info "语法：array.slice(start, end)"

        * start: Optional. Use negative numbers to select from the end of an array. If omitted, it acts like "0"
        * end: Optional. If omitted, all elements from the start position and to the end of the array will be selected. Use negative numbers to select from the end of an array

    返回值: A new Array, containing the selected elements


??? note "sort()"

    By default, the sort() method sorts the values as strings in alphabetical and ascending order (升序).

    Note: This method changes the original array.

    ??? info "语法：array.sort(compareFunction)"

        compareFunction: Optional. A function that defines an alternative sort order. The function should return a negative, zero, or positive value, depending on the arguments, like:

        * function(a, b){return a-b}

        When the sort() method compares two values, it sends the values to the compare function, and sorts the values according to the returned (negative, zero, positive) value.

        ??? success "Example:"

            When comparing 40 and 100, the sort() method calls the compare function(40,100).

            The function calculates 40-100, and returns -60 (a negative value).

            The sort function will sort 40 as a value lower than 100.

    返回值:	The Array object, with the items sorted


??? note "splice()"

    adds/removes items to/from an array, and returns the removed item(s).

    Note: This method changes the original array.

    ??? info "语法：array.splice(index, howmany, item1, ....., itemX)"

        * index: Required. An integer that specifies at what position to add/remove items, Use negative values to specify the position from the end of the array
        * howmany: Optional. The number of items to be removed. If set to 0, no items will be removed
        * item1, ..., itemX: Optional. The new item(s) to be added to the array

    返回值:	A new Array, containing the removed items (if any)


??? note "map()"

    map() 方法返回一个新数组，数组中的元素为原始数组元素调用函数处理后的值。

    map() 方法按照原始数组元素顺序依次处理元素。

    Note: map() does not execute the function for array elements without values.

    Note: 此方法不改变 the original array.

    ??? info "语法：array.map(function(currentValue, index, arr), thisValue)"

        * index: Optional. The array index of the current element
        * arr: Optional. The array object the current element belongs to
        * thisValue: Optional. A value to be passed to the function to be used as its "this" value. If this parameter is empty, the value "undefined" will be passed as its "this" value

    返回值:	An Array containing the results of calling the provided function for each element in the original array.


??? note "join()"

    The join() method returns the array as a string.

    The elements will be separated by a specified separator. The default separator is comma (,).

    Note: this method will not change the original array.

    ??? note "语法：array.join(separator)"

        separator: Optional. The separator to be used. If omitted, the elements are separated with a comma

    返回值:	A String, representing the array values, separated by the specified separator



