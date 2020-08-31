
> [JavaScript building blocks](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks)

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

请记住，某些内置 (built-in) 的浏览器函数不是 核心 (core) JavaScript 语言的一部分 - 某些被定义为浏览器 API 的一部分，这些 API 建立在默认语言的基础上，以提供更多功能。

??? note "Functions versus methods"

    程序员把函数称为对象方法（method）的一部分。

    到目前为止，我们使用的内置代码有两种形式：函数和方法。[built-in objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects)


??? note "匿名函数"

    * 通常，你将匿名函数与事件处理程序 (event handler) 一起使用
    * 你还可以将匿名函数分配为变量的值

* see also


## 4 创建自己的函数

??? note "显示消息框 (message box) 的条件"

    * new data being available, 
    * an error having occurred, 
    * the user trying to delete their profile ("are you sure about this?"), 
    * the user adding a new contact and the operation completing successfully, etc.

??? failure "错误"

    ``` javascript
    btn.onclick = displayMessage();
    ```

    在这种情况下，括号有时称为“函数调用运算符 (function invocation operator)”。仅当你要在当前作用域中立即运行函数时，才使用它们。同样，匿名函数内部的代码也不会立即运行，因为它在函数作用域内。

## 5 函数返回值

通常，在函数是某种计算的中间步骤的情况下，将使用返回值。您想要获得最终结果，其中涉及一些需要由函数计算的值。函数计算出值后，可以返回结果，以便将其存储在变量中；您可以在下一阶段的计算中使用此变量。

* see also

## 6 事件介绍

* [Event reference](https://developer.mozilla.org/en-US/docs/Web/Events)


每个可用事件都有一个事件处理程序 (event handler)。注意：事件处理程序 (event handlers) 有时也称为事件监听器 (event listeners) - they are pretty much interchangeable for our purposes, although strictly speaking, they work together. The listener listens out for the event happening, and the handler is the code that is run in response to it happening.

!!! note "Web 事件不是核心 JavaScript 语言的一部分 - 它们被定义为浏览器内置的 API 的一部分。"

??? note "不只是网页"

    值得一提的是事件不是 JavaScript 独有的 - 大多数编程语言都具有某种事件模型，并且该模型的工作方式通常与 JavaScript 的方式不同。In fact, the event model in JavaScript for web pages differs from the event model for JavaScript as it is used in other environments.

    例如, Node.js 是一个非常流行的 JavaScript runtime，它使开发人员能够使用 JavaScript 来构建网络 (network) 和服务器端应用程序。[Node.js event model](https://nodejs.org/docs/latest-v12.x/api/events.html) 依赖于监听器 (listeners) 监听事件和发射器 (emitters) 定期发射事件 — 
    
    它听起来没有那么不同，但代码是完全不同的，使用像 on() 的函数注册一个事件监听器，once() 注册一个运行一次后注销的事件监听器。[The HTTP connect event docs](https://nodejs.org/docs/latest-v12.x/api/http.html#http_event_connect) 提供了一个好例子。

### 使用 web events 的方式

??? note "1. Event handler properties"

    * .onclick
    * 其他

        * btn.onfocus 和 btn.onblur (tab 键 测试)

            > 它们通常用于当 focused 时，显示有关填写表单字段 (form fields) 的信息，或者 如果表单字段填充的值不正确则显示错误消息。

        * btn.ondblclick (双击)
        * window.onkeypress, window.onkeydown, window.onkeyup (键盘)
        * btn.onmouseover 和 btn.onmouseout

    有些事件是通用事件，几乎可以在任何地方使用（例如，onclick handler 可以在几乎任何元素上注册），而有些事件则更 specific，仅在某些情况下才有用（例如，onplay 仅在特定元素上，例如 `<video>` 使用是有意义的）。

!!! failure "2. Inline event handlers — don't use these"

??? note "[forEach()](https://developer.mozilla.org/en-US/docs/Web/API/NodeList)"

    ``` javascript
    const buttons = document.querySelectorAll('button');

    for (let i = 0; i < buttons.length; i++) {
      buttons[i].onclick = bgChange;
    }
    ```

    等价于 

    ``` javascript
    buttons.forEach(function(button) {
      button.onclick = bgChange;
    });
    ```

!!! note "注意：将您的编程逻辑与内容分开，也会使您的网站对搜索引擎更友好。"

??? note "3. addEventListener() and removeEventListener()"

    注意：将所有代码放在 addEventListener() 函数中的匿名函数中是非常合适的

    优点：

    1. 有一个对等函数 removeEventListener()，它删除了先前添加的监听器。
    2. 可以为同一个监听器 (listener) 注册多个处理程序 (handlers)

        ``` javascript
        // 第二行覆盖第一行的 onclick 设置的值
        myElement.onclick = functionA;
        myElement.onclick = functionB;
        ```

        ``` javascript
        // 两个函数都会运行
        myElement.addEventListener('click', functionA);
        myElement.addEventListener('click', functionB);
        ```

    3. other powerful features and options available

* 但不要担心，大多数 JavaScript 库（例如 jQuery）都具有内置函数，这些函数可以抽象化跨浏览器的差异。


### 其他 event 概念

??? note "Event objects"

    它会自动传递给事件处理程序以提供额外的功能和信息。

    事件对象的 target 属性始终是对事件发生所在元素的引用。

    当您要在多个元素上设置相同的事件处理程序并在事件发生时对所有元素执行某些操作时，e.target 非常有用。

    你遇到的大多数事件处理程序 (event handlers) 在事件对象 (event object) 上都有一组标准的属性 (properties) 和函数（方法）。see the [Event](https://developer.mozilla.org/en-US/docs/Web/API/Event) object reference for a full list. 但是，一些更高级的处理程序 (handlers) 会添加 包含 (they need to function) 的额外数据 的专家属性 (specialist properties)。如 Media Recorder API
    
??? note "阻止默认行为"

    最常见的示例是 Web form (表单)，例如 自定义注册表单。

    某些浏览器支持自动表单数据验证功能，但由于许多浏览器不支持，因此建议您不要依赖那些浏览器并实施自己的验证检查。

    ``` javascript
    form.onsubmit = function(e) {
      if (fname.value === '' || lname.value === '') {
        e.preventDefault();
        para.textContent = 'You need to fill in both names!';
      }
    }
    ```

??? abstract "Event bubbling and capture (事件冒泡和捕获)"

    你很少会遇到，但是如果你不了解，可能会感到非常痛苦。事件冒泡和捕获是两种机制，它们描述了当一个元素上有相同事件类型的两个处理程序 (handlers) 被激活时会发生什么。

    When an event is fired on an element that has parent elements (in this case, the `<video>` has the `<div>` as a parent), modern browsers run two different phases — the capturing phase and the bubbling phase.

    * In the capturing phase (在捕获阶段) :

        * 浏览器检查元素的最外祖先（outer-most ancestor, `<html>`）是否有 onclick event handler 在其上被注册了 for 捕获阶段，如果是，则运行该事件处理程序。
        * 然后，它继续前进到 (move on to)  `<html>` 内的下一个元素并执行相同的操作，然后执行下一个，依此类推，直到到达实际选择的元素。

    * 在冒泡阶段，正好相反：

        * 浏览器检查以查看所选元素是否有 onclick event handler 在其上被注册了 for 冒泡阶段，如果是，则运行该事件处理程序。
        * 然后，它继续移动到 (move on to) 下一个直接祖先元素 (immediate ancestor element) 并做相同的事，然后再下一个，依次类推，直到到达 `<html>` 元素为止。

    In modern browsers, by default, all event handlers are registered for the bubbling phase.

    ??? note 
    
        如果同时存在冒泡和捕获两种类型的事件处理程序，则捕获阶段将首先运行，然后是冒泡阶段。

    ??? note "使用 stopPropagation() 解决问题"
    
        ``` javascript
        video.onclick = function(e) { // handler
          e.stopPropagation(); // event object
          video.play();
        };
        ```

    !!! note "在糟糕的过去，浏览器的相互兼容性要比现在低得多，Netscape 仅使用事件捕获，而 Internet Explorer 仅使用事件冒泡。"

    ??? note "Event delegation (事件委托)"

        冒泡还允许我们利用事件委托 —— 这个概念依赖于以下事实: 如果你想要在大量子元素中单击任何一个都可以运行一段代码，您可以将事件监听器设置在它们的父节点上，并让子节点上发生的事件冒泡到父节点上，而不是每个子节点单独设置事件监听器。

        一个很好的例子是一系列列表项 (a series of list items)，如果你想让每个列表项被点击时弹出一条信息，您可以将 click event listener 设置在父元素 `<ul>` 上，这样事件就会从列表项冒泡到 `<ul>` 上。

        * [How JavaScript Event Delegation Works](https://davidwalsh.name/event-delegate)


* see also


## 7 图片库


