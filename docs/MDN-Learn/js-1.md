
> [Howto](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Howto)
>
> [First Steps](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps)

## 1 什么是 JavaScript ?

??? note "API"

    API 是现成的代码构建块集 (sets of code building blocks)，它们使开发人员能够实现原本很难或无法实现的程序。它们在编程方面的作用与现成的家具套件在住宅建筑中的作用相同 – 用一些已经切好的木板组装一个书柜，显然比自己设计，寻找合适的木材，裁切至合适的尺寸和形状，找到正确尺寸的螺钉，再组装成书柜要简单得多。

    它们通常分为两类。

    1. 浏览器 API 内置于你的 Web 浏览器中，能够暴露来自周围计算机环境的数据，或做有用的复杂工作。例如：

        * DOM API 允许你操作 HTML 和 CSS，创建，删除和修改 HTML，动态地应用新的样式到你的页面等。比如每一次你看到一个弹出窗口出现在页面上，或者显示一些新的内容，那就是 DOM 在运行。
        * Geolocation API
        * The Canvas and WebGL APIs
        * Audio and Video APIs

    2. 第三方 API

    JavaScript 的一种非常常见的用法是通过 DOM API 来动态修改 HTML 和 CSS 以更新用户界面。请注意，Web 文档中的代码通常按照其在页面上出现的顺序加载和执行。如果 JavaScript 在它所影响的 HTML 和 CSS 加载之前 加载并尝试运行，则可能会发生错误。


??? note "Interpreted (解释) versus compiled (编译) code"

    JavaScript 是一种轻量级的解释型编程语言。Web 浏览器以其原始文本形式接受 JavaScript 代码，并从中运行脚本。从技术角度来看，大多数现代 JavaScript 解释器 (interpreters) 实际上使用一种称为即时编译 (just-in-time compiling) 的技术来提高性能。当使用脚本时，JavaScript 源代码将被编译为更快的二进制格式，以便可以尽快运行。但是，JavaScript 仍被认为是一种解释语言，因为编译是在运行时而不是提前进行的。


??? note "Dynamic (动态) versus static (静态) code"

    动态这个词用来描述 客户端 JavaScript 和 服务器端语言 - 它是指 更新网页/应用程序的显示，以在不同环境下显示不同事物的能力，因为需要产生新的内容。服务器端代码在服务器上动态生成新内容，例如从数据库中提取数据 (pulling data)，而客户端 JavaScript 在客户端浏览器内部动态生成新内容，例如创建新的 HTML 表 (table)，用从服务器请求到的数据填充，然后在展示给用户的网页中显示表格 (table)。在这两种情况下，含义略有不同，但相互关联，并且通常这两种方法（服务器端和客户端）一起工作。

    没有动态更新内容的网页称为静态 - 它始终显示相同的内容。


??? note "脚本加载策略 (Script loading strategies)"

    在正确的时间获取脚本来加载涉及很多问题。没有看起来那么简单！一个常见的问题是页面上的所有 HTML 均以其出现顺序加载。如果你正在使用 JavaScript 来操纵页面上的元素（或更准确地说，是 Document Object Model），并且在你尝试执行操作的 HTML 之前加载并解析了 JavaScript，则代码将无法工作。

??? abstract "async and defer"

    实际上，我们可以使用两个现代功能 (features) 来绕过阻塞脚本的问题 - async 和 defer。让我们看一下两者之间的区别。

    ??? note "async"

        使用 async 属性加载的脚本不会阻塞渲染页面而将下载脚本，并在脚本完成下载后立即执行。您无法保证脚本将以任何特定的顺序运行，仅能确保它们不会阻止页面其余部分的显示。最好当页面中的脚本彼此独立运行并且不依赖页面上的其他脚本时，使用 async。

        您不能依赖脚本加载的顺序。

        当您有许多后台脚本要加载时应该使用 async，而您只想尽快将它们安装到位。例如，也许您要加载一些游戏数据文件，当游戏真正开始时将需要这些文件，但现在您只需要继续显示游戏介绍，标题和大厅，而不会被 脚本加载 所阻塞。


    ??? note "defer"

        使用 defer 属性的脚本将按照它们在页面中出现的顺序加载运行，并在下载脚本和内容后立即执行它们：

        在 外部JavaScript 中，我们使用一种更现代的 JavaScript 功能 (feature) 来解决该问题，即 defer 属性，该属性指示浏览器在到达 `<script>` 元素后继续下载 HTML 内容。

        在这种情况下，脚本 和 HTML 将同时加载，并且代码将起作用。它们要等到页面内容全部加载后才能运行，如果脚本依赖于 DOM（例如，它们修改页面上的多个元素之一），这将很有用。

        ??? note "注意"

            在外部情况下，我们不需要使用 DOMContentLoaded 事件，因为 defer 属性为我们解决了问题。对于内部 JavaScript 示例，我们没有使用 defer 解决方案，因为 defer 仅适用于外部脚本。


    ??? summary "总结"

        * async 和 defer 都指示浏览器在一个单独线程下载 script(s)，而网页（DOM 等）的其余部分正在下载，所以 网页加载 不会被脚本阻塞。
        * 如果您的脚本应该立即运行并且没有任何依赖关系，请使用 async。
        * 如果您的脚本需要等待解析并且依赖于其他脚本 和/或 DOM，请使用 defer 加载它们 并将相应的 `<script>` 元素按所需顺序放置。


## 2 JavaScript 初体验


??? note "Events"

    The constructs that listen out for the event happening are called event listeners, and the blocks of code that run in response to the event firing are called event handlers.

??? note "Object"

    在 JavaScript 中，一切皆对象。对象是存储在单个分组中的相关功能 (functionality) 的集合 (collection) 。

    built-in (内建) objects

    * "[Document](https://developer.mozilla.org/en-US/docs/Web/API/Document)"

        method:

        * [querySelector()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)

            > 由于 guessField 现在包含对 `<input>` 元素的引用，因此它现在可以访问许多属性（properties, 基本上是存储在对象内部的变量，其中一些不能更改其值）和方法（methods, 基本上是存储在对象内部的函数）。input 元素可用的一个 method 是 focus()，因此我们现在可以使用此行来 focus 文本输入：


??? note "其他"

    * 浏览器返回 undefined, 因为 paragraphs 没有 value property.
    * console 自动补全 存在于执行环境内的对象名，包括变量。
    * 页面上的每个元素都有一个 style property，该 property 本身包含一个对象，该对象的 propertyies 包含应用于该元素的所有 inline CSS 样式。这允许我们使用 JavaScript 在元素上 动态设置 新的 CSS 样式。




## 3 解决错误

??? note "Null"

    Null 是一个特殊值，表示 “nothing” 或 “no value”。因此 lowOrHi 已经被声明 (declared) 和初始化，但是没有任何有意义的值 - 它没有类型或值。

??? note "scope 作用域"

    加载页面后不会立即出现此错误，因为此错误发生在函数内部（在 checkGuess() { ... } 块内部）。正如您将在后面的函数文章中更详细地了解的那样，函数内部的代码在独立于函数外部的代码的作用域内运行。在这种情况下，直到 checkGuess() 函数由第86行运行时，代码才运行，并且抛出错误。


## 4 变量

??? note "We say variables contain values." 

    我们说变量包含值。这是一个重要的区别。变量本身不是值。它们是值的容器。你可以认为它们就像是可以用来存放东西的小纸板盒。

??? note "var 和 let 之间的区别"

    最初创建 JavaScript 时，只有 var。在大多数情况下，这基本上可以正常工作，但是在工作方式上存在一些问题 - 其设计有时会令人困惑或令人生厌。因此，在现代版本的 JavaScript 中创建了 let，这是一个用于创建变量的新关键字，该变量的工作方式与 var 稍有不同，从而解决了该问题。

    下面说明几个简单的区别。我们现在不会介绍所有差异，但是随着您对JavaScript的更多了解，您将开始发现它们（如果您现在真的想阅读它们，请随时查看我们的let参考页）。

    1. [var hoisting](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var#var_hoisting)
    2. var 可以根据需要多次声明同一变量，但是 let 不行

??? note "变量命名规则"

    * 通常，你应该只使用拉丁字符（0-9，a-z，A-Z）和下划线字符。
    * 不要在变量名的开头使用下划线 - 在某些 JavaScript 结构 (constructs) 中使用此符号表示 specific things，因此可能会造成混淆。
    * 不要在变量开头使用数字。不允许这样做，会导致错误。
    * lower camel case
    * [保留关键字](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Keywords)


??? note "变量类型"

    * Numbers
    * Strings
    * Booleans
    * Arrays
    * Objects

??? note "Dynamic typing (动态类型)"

    JavaScript is a "dynamically typed language"

??? note "const"

    const 的工作方式与 let 完全相同，除了你无法给 const 新值。


## 5 JavaScript 中的基础数学 — 数字和操作符 (operators)

第二个好消息是，与一些其他编程语言不同，JavaScript 只有一种数据类型用来表示数字（包括 integers 和 decimals），您猜对了，Number。这意味着无论您使用 JavaScript 处理哪种类型的数字，都以完全相同的方式处理它们。

!!! note "实际上，JavaScript 具有第二个数字类型 BigInt，用于非常大的整数。"

??? note "Useful Number methods"

    * toFixed()

??? note "Converting to number data types"

    将 字符串值 传递到 Number() 构造函数 (constructor) 中以返回相同值的数字版本。

??? note "[operator precedence (运算符优先级)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#Operator_precedence)"

    在计算 计算（calculation，在编程中称为表达式，expression）结果时，一些运算符 (operators) 会先于其他运算符应用。


!!! note "[Assignment operators (赋值运算符)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#Assignment_operators)"


??? note "==="

    * ===	Strict equality
    * !==	Strict-non-equality

    `== / !=` 测试值是否相同， 但是不测试值的数据类型是否相同，`=== / !==` 严格版本 测试值和数据类型是否相同。严格的版本通常导致更少的错误，因此我们建议您使用它们。

* [Numbers and dates](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Numbers_and_dates)
* [Expressions and operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators)


## 6 处理文本 - JavaScript 中的字符串

??? note "Escaping characters (转义字符)"

    [Escape notation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#Escape_notation)


!!! note "注意：当你在代码中输入实际字符串时，这个用单引号或双引号括起来的字符串称为 字符串字面值 (string literal)。"

??? note "two constructs"

    * 如果可以的话，Number 对象 将把传递给它的任何东西转换成一个数字。
    * 相反，每个数字都有一个称为 toString() 的 method 将其转换为等价字符串。

??? note "[Template literals (模板字面值)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)"

    * 当您想在字符串中包含变量或表达式时，可以将其包含在 ${ } 构造 (construct) 中，称为占位符 (placeholder) 。
    * 不需要换行符

## 7 Useful string methods

> Strings as objects

* [String object page](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

??? note "常用"

    * 找到长度 length
    * 检索特定字符 [length-1]
    * 找到并提取子字符串 
        * indexOf()
        * slice()

            ``` javascript
            browserType.slice(0,3);
            ```

            ``` javascript
            browserType.slice(2);
            ```

    * 改变大小写 toLowerCase() / toUpperCase()
    * 更新字符串的一部分 replace()

        ``` javascript
        browserType = browserType.replace('moz','van');
        ```

## 8 数组

我们可以存储各种数据类型在数组中 - 字符串，数字，对象，甚至其他数组。我们还可以在单​​个数组中混合数据类型

注意，数组内部的数组称为多维数组。

* 找到长度 .length

??? note "有用的数组 methods"

    * 在字符串和数组之间转换

        * 字符串到数组

            split(): 从技术上讲，这是一个字符串方法，而不是数组方法，但是我们将其与数组放在一起，因为它在这里进展顺利。

        * 数组到字符串

            join(): 以相反的方式进行操作
            toString(): 使用 join() 可以指定不同的分隔符，而 toString() 始终使用逗号。

    * 添加和删​​除数组项

        * 数组末尾：push() / pop()

            ``` javascript
            // 包含一个或多个 items
            myArray.push('Bradford', 'Brighton');
            ```

        * 数组开头: unshift() / shift()


* [Indexed collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
* [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)



