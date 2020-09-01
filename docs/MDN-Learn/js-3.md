
> [JavaScript 对象入门](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects)

在 JavaScript 中，大多数东西都是对象，从 core JavaScript features 如数组 到 建立在 JavaScript 之上的浏览器 APIs。您甚至可以创建自己的对象，以将相关函数和变量封装 (encapsulate) 到高效的 packages 中，并充当方便的数据容器。如果您想进一步了解该语言，理解 JavaScript 的基于对象的本质 (object-based nature) 很重要。

## 1 对象基础

??? note "对象基础"

    对象是相关数据 和/或 功能 (functionality) 的集合（collection, 通常由几个变量和函数组成 - 当它们位于对象内部时称为 属性 (properties) 和方法 (methods) 。）

    一个对象由多个成员 (members) 组成，每个成员都有一个名称（name, 例如 name 和 age）和一个值（value, 例如['Bob', 'Smith'] 和 32）。每个 名称/值 对必须用逗号分隔，并且名称和值在每种情况下都用冒号分隔。语法始终遵循以下模式：

    ``` javascript
    const objectName = {
      member1Name: member1Value,
      member2Name: member2Value,
      member3Name: member3Value
    };
    ```

    对象成员的值几乎可以是任何东西 - 在我们的 person 对象中，我们有一个字符串，一个数字，两个数组和两个函数。前四个 items 是 data items，被称为对象的属性 (properties) 。最后两个 items 是允许对象使用该数据执行某些操作 (do something) 的函数，被称为对象的方法 (methods) 。

    像这样的对象称为对象字面量 (object literal) - 在创建对象时，我们已经照字面写出了对象内容 (literally written out the object contents)。这与从类实例化的对象 (objects instantiated from classes) 形成对比，我们将在后面讨论。

    当您想以某种方式传输一系列结构化的相关数据项时，例如使用向服务器发送请求以将其放入数据库中，使用对象字面量创建对象是很常见的。发送单个对象比单独发送多个项目要有效得多，并且当您要通过名称 (name) 标识 (identify) 单个项目时，比数组更容易使用。


??? abstract "Dot notation (点表示法) "

    对象名称 (name) 充当 (act as) 命名空间 (namespace) - 必须首先输入它才能访问封装在对象内部的所有内容。接下来，您写一个点，然后是要访问的项目 - 这可以是简单属性 (property) 的名称 (name) ，数组属性的一项 或 对一个对象方法的调用，例如：

    ``` javascript
    person.age
    person.interests[1]
    person.bio()
    ```

    ??? note "Sub-namespaces (子命名空间)"

        甚至可以用一个对象来做另一个对象成员的值。例如，将 name 成员

        ``` javascript
        name: ['Bob', 'Smith'],
        ```

        改成

        ``` javascript
        name : {
          first: 'Bob',
          last: 'Smith'
        },
        ```

        在这里，我们实际上创建了一个子命名空间。这听起来很复杂，但实际上并非如此 - 要访问这些项目，您只需要 chain the extra step onto the end with another dot。

        ``` javascript
        person.name.first
        person.name.last
        ```

        ??? important "methods 也要改"

        ``` javascript
        name[0]
        name[1]
        ```

        改为

        ``` javascript
        name.first
        name.last
        ```

??? note "Bracket notation (括号表示法)"

    另一种访问对象属性 (properties) 的方法

    ``` javascript
    person.age
    person.name.first
    ```

    可以是

    ``` javascript
    person['age']
    person['name']['first']
    ```

    这看起来与访问数组中的项目的方式非常相似，并且基本上是同一件事 – 不是使用索引号 (index number) 来选择项目，而是使用与每个成员 (member) 的 value 关联的 name。难怪对象有时被称为关联数组 (associative arrays) - 它们将字符串映射到值的方式与数组将数字映射到值的方式相同。


??? note "Setting object members (设置对象成员)"

    * retrieving (or getting) object members
    * set (update) the value of object members

    ``` javascript
    person.age = 45;
    person['name']['last'] = 'Cratchit';
    ```

    设置成员不只可以更新现有属性和方法的值。你也可以创建全新的成员。

    括号表示法的一个有用方面是，它不仅可用于动态设置成员值，而且还可用于设置成员名。

    ``` javascript
    let myDataName = nameInput.value;
    let myDataValue = nameValue.value;
    ```

    然后，我们可以将这个新的成员名称和值添加到 person 对象中

    ``` javascript
    person[myDataName] = myDataValue;
    ```

    点表示法无法使用上述方法向对象添加属性，点表示法只能接受 a literal member name，而不能接受指向 name 的变量值


??? note "this"

    this 关键字 是指 (refers to) the current object the code is being written inside - 所以在这种情况下，this 等同于 person。那么，为什么不直接写 person 呢？当我们开始创建构造函数 (start creating constructors) 等时，this 非常有用 - 它始终确保在成员的上下文 (a member's context) 更改时使用正确的值（例如，两个不同的 person 对象实例 (instances) 可能有不同的 names，但当我们调用它们的 greeting 时 想要使用它们自己的 name）。

    ``` javascript
    const person1 = {
      name: 'Chris',
      greeting: function() {
        alert('Hi! I\'m ' + this.name + '.');
      }
    }

    const person2 = {
      name: 'Deepti',
      greeting: function() {
        alert('Hi! I\'m ' + this.name + '.');
      }
    }
    ```

    如前所述，this 等于 the object the code is inside - 用手编写对象字面量 (object literals) 时这并不是很有用，但是当您动态生成对象（例如使用构造函数 (constructors)）时，它确实会发挥作用。


??? abstract "你一直在使用对象"

    ``` javascript
    myString.split(',');
    ```

    You were using a method available on an instance of the [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) class. Every time you create a string in your code, that string is automatically created as an instance of String, and therefore has several common methods and properties available on it.

    ``` javascript
    const myDiv = document.createElement('div');
    const myVideo = document.querySelector('video');
    ```

    You were using methods available on an instance of the [Document](https://developer.mozilla.org/en-US/docs/Web/API/Document) class. For each webpage loaded, an instance of Document is created, called document, which represents the entire page's structure, content, and other features such as its URL. Again, this means that it has several common methods and properties available on it.

    ??? note "内置对象和 API 并非总是自动创建对象实例"

        Notifications API，要求你使用构造函数为要触发的每个通知实例化一个新的对象实例
        
        ``` javascript
        const myNotification = new Notification('Hello!');
        ```

    ??? note

        It is useful to think about the way objects communicate as message passing — 当一个对象需要另一个对象执行某种操作 (action) 时，它通常会通过 one of its methods 将消息发送给另一个对象，并等待响应 (response) ，即我们所知的返回值。


## 2 Object-oriented (面向对象) JavaScript for beginners





