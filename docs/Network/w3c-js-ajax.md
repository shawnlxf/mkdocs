
## [AJAX (Asynchronous JavaScript And XML)](https://www.w3schools.com/js/js_ajax_intro.asp)


??? info

    AJAX 不是编程语言，是从 web page 访问 web servers 的技术。

    AJAX just uses a combination of:

    * A browser built-in `XMLHttpRequest` object (to request data from a web server)
    * JavaScript and HTML DOM (to display or use the data)

    ??? info "AJAX is a misleading name."
    
        AJAX applications might use XML to transport data, but it is equally common to transport data as plain text or JSON text.

    AJAX 允许网页 to be updated asynchronously 通过在后台与 web server 交换数据. 这意味着可以在不重新加载整个页面的情况下 update 部分 web page.

    The XMLHttpRequest object can be used to exchange data with a web server behind the scenes. This means that it is possible to update parts of a web page, without reloading the whole page.

??? question "How AJAX Works"

    ![](../img/Network/pic_ajax.gif)

    1. An event occurs in a web page (the page is loaded, a button is clicked)
    2. An XMLHttpRequest object is created by JavaScript
    3. The XMLHttpRequest object sends a request to a web server
    4. The server processes the request
    5. The server sends a response back to the web page
    6. The response is read by JavaScript
    7. Proper action (like page update) is performed by JavaScript

* [XMLHttpRequest Object Methods / Properties](https://www.w3schools.com/js/js_ajax_http.asp)
* [XMLHttpRequest 封装](https://www.w3schools.com/js/js_ajax_http_response.asp)


## MDN

??? info "[MDN-AJAX](https://developer.mozilla.org/en-US/docs/Web/Guide/AJAX)"

    including JSON, XML, HTML, and text files

    Although X in Ajax stands for XML, JSON is used more than XML nowadays because of its many advantages such as being lighter and a part of JavaScript. Both JSON and XML are used for packaging information in the Ajax model.

??? abstract "[MDN-XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)"

    * [XMLHttpRequest.readyState](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/readyState)
    * [Sending and Receiving Binary Data](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Sending_and_Receiving_Binary_Data)
    * [Using XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest)
    * [HTML in XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/HTML_in_XMLHttpRequest)



* [MDN-Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)

??? abstract "[MDN 入门](https://developer.mozilla.org/en-US/docs/Web/Guide/AJAX/Getting_Started)"

    In a nutshell, it is the use of the XMLHttpRequest object to communicate with servers. It can send and receive information in various formats, including JSON, XML, HTML, and text files.

    ??? note "The two major features of AJAX allow you to do the following:"

        * Make requests to the server without reloading the page
        * Receive and work with data from the server

    ??? note "您可以通过两种方式访问​​该数据："

        * httpRequest.responseText – 以文本字符串形式返回服务器响应
        * httpRequest.responseXML – 将响应作为 XMLDocument 对象返回，可以使用 JavaScript DOM 函数遍历

    bypassing the cache




* Tools: [axios](https://github.com/axios/axios): Promise based HTTP client, which uses XMLHttpRequest internally.


??? abstract "[MDN Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)"

    The Promise object represents the eventual completion (or failure) of an asynchronous operation and its resulting value.

    这使异步方法像同步方法一样返回值：instead of immediately returning the final value, the asynchronous method returns a promise to supply the value at some point in the future.

    A Promise 处于以下状态之一：

    * pending: initial state, neither fulfilled nor rejected.
    * fulfilled: meaning that the operation was completed successfully.
    * rejected: meaning that the operation failed.

    When either of these options happens, the associated handlers queued up by a promise's then method are called.


??? abstract "[Using Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)"

    本质上 Promise 是一个函数返回的对象，我们可以在它上面绑定回调函数 (attach callbacks)，这样我们就不需要在一开始把回调函数作为参数传入这个函数了。

    ``` javascript
    createAudioFileAsync(audioSettings).then(successCallback, failureCallback);
    ```

    That's shorthand for:

    ``` javascript
    const promise = createAudioFileAsync(audioSettings); 
    promise.then(successCallback, failureCallback);
    ```

    异步函数调用(asynchronous function call)

    ??? note "Guarantees (保证)"

        Unlike old-fashioned passed-in callbacks, a promise comes with some guarantees:

        * Callbacks will never be called before the completion of the current run of the JavaScript event loop.
        * Callbacks added with then(), as above, will be called even after the success or failure of the asynchronous operation.
        * Multiple callbacks may be added by calling then() several times. Each callback is executed one after another, in the order in which they were inserted.

        One of the great things about using promises is chaining (链式调用).




## Blog

??? note "[JavaScript Promises for Dummies](https://www.digitalocean.com/community/tutorials/javascript-promises-for-dummies)"

    Anything that need to wait for promise to proceed, you put that in `.then`.








