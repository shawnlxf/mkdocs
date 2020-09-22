
## [Window Object](https://www.w3schools.com/jsref/obj_window.asp)

??? info

    The window object represents an open window in a browser.

    If a document contain frames (`<iframe>` tags), the browser creates one window object for the HTML document, and one additional window object for each frame.

??? note "setInterval()"

    setInterval() 方法可按照指定的周期（以毫秒计）来调用函数或计算表达式。

    setInterval() 方法会不停地调用函数，直到 clearInterval() 被调用或窗口被关闭。

    返回值:	A Number, representing the ID value of the timer that is set. Use this value with the clearInterval() method to cancel the timer

    ??? tip

        如果你只想执行函数一次可以使用 setTimeout() 方法。

    语法：setInterval(function, milliseconds, param1, param2, ...)

??? note "clearInterval()"

    clearInterval() 方法 clears 由 setInterval() 方法设定的 timer。

    clearInterval() 方法的参数必须是由 setInterval() 返回的 ID 值。

    语法：clearInterval(var)


??? note "setTimeout()"

    setTimeout() 方法用于在指定的毫秒数后调用函数或计算表达式。

    ??? tip

        使用 clearTimeout() 方法来阻止函数的执行。

    语法：setTimeout(function, milliseconds, param1, param2, ...)

    返回值:	A Number, representing the ID value of the timer that is set. Use this value with the clearTimeout() method to cancel the timer