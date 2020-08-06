# 重要标签

## 1 a 标签

??? quote "作用：(href)"

    1. 跳转外部页面，文件
    2. 跳转内部锚点
    3. 跳转到邮箱或电话等

??? note "属性 href"

    1. 网址  

        * https://google.com  
        * http://google.com  
        * //google.com (自动选择用 http 还是 https)

    2. 路径  

        * /a/b/c (http 服务的根目录) 以及 a/b/c  
        * index.html 以及 ./index.html

    3. 伪协议  

        * javascript:代码;  
        * mailto:邮箱  
        * tel:手机号

    4. id，同一页面上的元素  

        * href="#xxx"

            > 注意: 你可以使用 href="#top" 或 空片段 (empty fragment) (href="#") 链接到当前页面的顶部

??? note "属性 target"

    > 在何处显示链接的 URL，作为 浏览上下文 (browsing context, 如 a tab, window 或 <iframe\>) 的名字

    1. 内置名字  

        * \_self (默认)

            > 当前浏览上下文

        * \_blank

            > usually a new tab, 但是用户可以配置浏览器来打开新窗口.

        * \_parent

            > 当前浏览上下文的父浏览上下文. 如果没有 parent, 表现为 \_self.

        * \_top
          
            > 最高浏览上下文 ("最高" 上下文是当前浏览上下文的祖先). 如果没有祖先，则表现为 _self。

    2. 程序员命名  

        * window 的 name

            > Console -> window.name

        * iframe 的 name

??? note "属性 download"

    保存链接的 URL，可以 有值 或 没有值

    * 没有值
    * 有值

    问题：不是所有浏览器都支持，尤其是手机浏览器可能不支持

??? failure "onclick 事件"

    `<a>` 经常被滥用作为假按钮，通过设置 href 为 `#` 或 `javascript:void(0)` 来阻止页面刷新, 然后监听其 click 事件.

    当复制/拖动链接，在新标签页/窗口中打开链接，添加书签或加载，错误或禁用 JavaScript 时，这些假的 `href` 值会导致 unexpected behavior。

    改用 `<button>`。通常，只应使用超链接用来导航到真实的 URL。

* rel="noopener"


## 2 img 标签

!!! quote "作用: 发出 get 请求，展示一张图片"

??? note "属性"

    * src  

        图像 URL. 强制的.

    * alt

        定义图像的 alternative text description。

    * height

        图像的 intrinsic 高度, 以像素为单位. 必须是不带单位的整数.

        可以只指定 width 和 height 中的一个值，浏览器会根据原始图像进行缩放。

    * width

        图像的 intrinsic 宽度, 以像素为单位. 必须是不带单位的整数.


!!! quote "事件"

    onload / onerror

!!! quote "响应式"

    [max-width: 100%](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Sizing_items_in_CSS/#min-_and_max-_sizes)

* [可替换元素(CSS)](https://developer.mozilla.org/en-US/docs/Web/CSS/Replaced_element)

## 3 表格内容 (Table content)

> 标签里只能有 3 个标签

??? note "`<table>`: 见例子"

    * 相关的样式

        * table-layout  
        * border-collapse  
        * border-spacing

    ``` css
    table {   
      border-collapse: collapse;    //border合并 
      border-spacing: 0             //for IE 
    }    
    ```

??? note "`<caption>`"

    > caption (or title)

    `<caption>`元素 应该是其父 `<table>` 元素的第一个孩子.

    > 如果包含 `<caption>` 的 `<table>` 元素是 `<figure>` 元素的唯一后代，则应使用 `<figcaption>` 元素代替`<caption>`。


!!! note "`<thead>`"

??? note "`<tbody>`"

    每个表格可以使用多于 1 个 `<tbody>`，只要它们都是连续的即可。

    这使您可以将大表中的行划分为多个部分，如果需要，可以分别设置每个部分的格式。


!!! note "`<tfoot>`"

!!! note "`<tr>`: 定义表格的 a row of cells"

??? note "`<td>`"

    定义 a cell of a table that contains data. 它参与 table model.

    * 属性 

        * colspan
        * headers

            > 此属性包含以空格分隔的字符串列表，每个字符串都与应用于此元素的`<th>` 元素的 id 属性相对应 。

        * rowspan


??? abstract "`<th>`"

    `<th>` 元素定义 a cell 作为一组 table cells 的 header。
    
    该组的确切性质由 scope 和 headers 属性定义。

    * 属性

        * abbr
        * headers

            > 此属性包含以空格分隔的字符串列表，每个字符串都与应用于此元素的`<th>` 元素的 id 属性相对应 。

        * colspan
        * rowspan
        * scope

            > 这个枚举属性定义了表头 (header) 元素 (在 `<th>` 中定义) 关联的单元格(cell). 它可能有以下值:

            * row: 表头关联其所属行中所有的单元格。
            * col: 表头关联其所属列中所有的单元格。
            * rowgroup: 表头属于一个行组并与其中所有单元格相关联。这些单元格可以被放在表头的左侧或右侧，取决于 `<table>` 元素中 dir 属性的值 。
            * colgroup: 表头属于一个列组并与其中所有单元格相关联。
            * auto (默认值)


??? note "`<colgroup>`"

    定义表格内的一组列。

    * 属性 span

        此属性包含一个正整数，指示该 `<colgroup>` 元素跨越的连续列数。如果不存在，则默认值为1。


## 4 Forms (表单)

??? abstract "`<form>`: 见例子"

    * 作用: 发 get 或 post 请求，然后刷新页面
    * 事件: onsubmit
    * 其他

        * form 必须要有一个 type="submit"的按钮  
        * button 里如果不写 type，则默认为 submit

    ??? note "属性"

        * autocomplete

            指示默认情况下输入元素是否可以由浏览器自动补全其值。
            
            此设定可以被属于此表单的子元素的 autocomplete 属性覆盖。
            
            可能的值有：
            

            * off：浏览器可能不会自动补全条目 (entries)。（在疑似登录表单中，浏览器倾向于忽略该值，而提供密码自动填充功能，参见 [The autocomplete attribute and login fields](https://developer.mozilla.org/en-US/docs/Web/Security/Securing_your_site/Turning_off_form_autocompletion#The_autocomplete_attribute_and_login_fields)）
            * on：浏览器可能会自动补全条目 (entries)。

        > 以下为关于表单提交的属性

        1. action

            处理表单提交的 URL。这个值可被 `<button>`、`<input type="submit">` 或 `<input type="image">` 元素上的 formaction 属性覆盖。

        * method

            提交表单的 HTTP 方法。可能的（不区分大小写）值有：

            * post: The [POST method](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html#sec9.5); 表单数据作为 [request body](https://developer.mozilla.org/en-US/docs/Web/API/Body) 发送.

            * get: The [GET method](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html#sec9.3); 表单数据会附加在 action URL 中，并以 '?' 作为分隔符，当表单[没有副作用](https://developer.mozilla.org/en-US/docs/Glossary/Idempotent)时使用这个方法。

            * dialog: 如果表单在 `<dialog>` 元素中，提交时关闭对话框。

            此值可以被 `<button>`、`<input type="submit">` 或 `<input type="image">` 元素中的 formmethod 属性覆盖。

        * target

            指示在提交表单之后，在哪里显示响应 (response)。

            在 HTML 4 中, 这是一个 frame 的名字/关键字对 (name/keyword)。
            
            在 HTML5 中，这是一个浏览上下文 (browsing context)（如标签页 tab、窗口 window 或 iframe） 的名字/关键字。
            
            以下关键字具有特殊含义：

            * _self (默认): 加载到与当前浏览上下文相同的浏览上下文中。
            * _blank: 加载到新的未命名浏览上下文中。
            * _parent: 加载到当前上下文的父级浏览上下文中。如果没有父级 (parent)，则与 _self 表现一致。
            * _top: 加载到顶级 (top-level) 的浏览上下文中（即当前上下文的一个祖先浏览上下文，并且没有父级）。如果没有父级，则与 _self 表现一致。

            此值可以被 `<button>`、 `<input type="submit">` 或 `<input type="image">` 元素中的 formtarget 属性覆盖。


  
??? abstract "`<input>`: 见例子"

    > 最强大和复杂的元素之一，因为 input 的 types 和 attributes 的组合有很多

    * 作用: 让用户输入内容

    ??? note "[`<input>` 类型](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/#<input>_types)"

        1. text (默认值): 单行文本字段 (field)。换行符 (Line-breaks) 会自动从输入值中删除。
        * search: 用于输入搜索字符串的单行文本字段 (field) 。换行符 (Line-breaks) 会自动从输入值中删除。在支持的浏览器中可能包含删除图标，可用于清除该字段。
        * checkbox: 复选框
        * radio: 单选按钮，允许从具有相同 name 值的多个选项中选择一个值。
        * submit: 用于提交表单的按钮。
        * range: 此控件用于输入不需要精确的数字。默认显示在中间值。结合使用 min 和 max 定义可接受值的范围。
        * hidden: 不显示的控件，其值仍会提交到服务器。

    ??? note "[其他 Attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#Attributes)"

        `<input>` 元素因其属性而非常强大，上面的 type 属性最重要. 

        > 由于每个 `<input>` 元素（无论类型如何）都基于 HTMLInputElement 接口，因此从技术上讲，它们共享完全相同的属性集。
        > 
        > 但是，实际上，大多数属性仅对输入类型的特定子集有影响。
        > 
        > 另外，某些属性影响输入的方式取决于输入类型，以不同的方式影响不同的输入类型。

        1. name / value: all

        * required: almost all

            > Boolean. A value is required(必填) 或 提交表单前必须先检查该值

        * multiple: email, file	

            > Boolean. 是否允许多个值

        * accept: file	

            > 用于规定(hint) 文件上传控件 中 期望的文件类型

        * width: image	

            > 与 `<img>` 的 width 属性一样

        * alt: image

            > image 类型的 alt 属性. Required for accessibility

        * src: image
          
            > 和 `<img>` 的 src 属性一样；图像资源的地址

        * autofocus: all

            > 页面加载时自动聚焦到此表单控件

        * checked: radio, checkbox
          
            > 命令 (command) 或 控件 (control) 是否被选中 (checked)

        * disabled: all	
          
            > 表单控件是否被禁用 (disabled)

        * maxlength: password, search, tel, text, url	
          
            > value 的最大长度（字符数）

        * pattern: password, text, tel	
          
            > Pattern the value must match to be valid


    * 事件: onchange / onfocus / onblur

    * 验证器: HTML5 新增功能

    ??? note "其他"

        * input type="submit" 和 button type="submit"的区别：

            * button 里可以加其他东西，如图片，strong 标签
            * input 不行

        * input: hidden 用来给 js 自动填 ID、字符串等

??? note "`<label>`"




* 标签

    * select + option
    * textarea
    * label

??? note "注意事项"

    * 一般不监听 input 的 click 事件
    * form 里面的 input 要有 name
    * form 里要放一个 type=submit 才能触发 submit 事件
