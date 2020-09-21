
## [AJAX (Asynchronous JavaScript And XML)](https://www.w3schools.com/js/js_ajax_intro.asp)

??? note "AJAX 是开发者的梦想，因为你可以："

    * Read data from a web server - after the page has loaded
    * Update a web page without reloading the page
    * Send data to a web server - in the background

??? info

    AJAX 不是编程语言，是从 web page 访问 web servers 的技术。

    AJAX just uses a combination of:

    * A browser built-in XMLHttpRequest object (to request data from a web server)
    * JavaScript and HTML DOM (to display or use the data)

    ??? info "AJAX is a misleading name."
    
        AJAX applications might use XML to transport data, but it is equally common to transport data as plain text or JSON text.

    AJAX 允许网页 to be updated asynchronously 通过在后台与 web server 交换数据. 这意味着可以在不重新加载整个页面的情况下 update 部分 web page.

??? question "How AJAX Works"

    ![](../img/Network/pic_ajax.gif)

    1. An event occurs in a web page (the page is loaded, a button is clicked)
    2. An XMLHttpRequest object is created by JavaScript
    3. The XMLHttpRequest object sends a request to a web server
    4. The server processes the request
    5. The server sends a response back to the web page
    6. The response is read by JavaScript
    7. Proper action (like page update) is performed by JavaScript



