# 全局属性

> Global attributes
>
> 所有标签都有的属性

??? note "1. class"

    以空格分隔的元素的 classes 列表。
    
    Classes 允许 CSS 和 JavaScript 通过 类选择器 或 函数比如 DOM 方法 `document.getElementsByClassName()` 选择和访问特定元素。

??? note "2. contenteditable"

    一个枚举属性，指示元素是否可被用户编辑。如果可以，浏览器将修改其 widget 以允许编辑。
    
    该属性必须采用以下值之一：

    * true 或 空字符串，表示该元素是可编辑的；
    * false，表示该元素是不可编辑的。

    如果属性没有值，例如 `#!html <label contenteditable>Example Label</label>`，则将其值视为空字符串。

    如果 缺少此属性 或 其值无效，则其值将从其父元素继承：因此，如果其父元素可编辑，则该元素是可编辑的。

    请注意，尽管其允许的值包括 true 和 false，但此属性是枚举值而不是布尔值。

    你可以使用 CSS `#!css caret-color` 属性 (property) 设置用于绘制文本插入 caret 的颜色。


??? note "3. hidden"

    布尔属性 (attribute)，表示该元素尚未 或 不再 相关。
    
    例如，它可用于隐藏 在登录过程完成之前 无法使用的页面元素。
    
    浏览器不会渲染此类元素。
    
    不得使用此属性隐藏可合法显示的内容。

??? note "4. id"

    定义了一个全文档唯一的标识符 (ID)。
    
    其目的是在链接（使用片段标识符, [fragment identifier](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Identifying_resources_on_the_Web#Fragment)），脚本或样式（使用CSS）时标识元素。


??? note "5. style"

    包含要应用于元素的 CSS 样式声明。
    
    请注意，建议在一个或多个单独的文件中定义样式。
    
    该属性和 `<style>` 元素的主要目的是允许进行快速样式化，例如用于测试目的。


??? note "6. tabindex"

    整数属性，指示元素是否可以获取输入焦点（可聚焦），是否应该参与顺序键盘导航，如果是，则表示哪个位置。（通常使用 Tab 键，因此得名）。
    
    有多个值可选：

    * 负值 表示该元素应该是可聚焦的，但不应通过顺序键盘导航可到达;

    * 0 表示元素应通过顺序键盘导航可聚焦和可到达，但其相对顺序由平台约定定义;

    * If several elements share the same tabindex, their relative order follows their relative positions in the document.

    * 正值 意味着元素应该通过顺序键盘导航 可聚焦和可访问; 元素聚焦的顺序是 tabindex 的递增值。如果多个元素共享相同的 tabindex，则它们的相对顺序遵循它们在文档中的相对位置。


??? note "7. title"

    包含表示与其所属元素相关的咨询信息的文本。
    
    这样的信息通常可以作为工具提示 (tooltip) 呈现给用户，但不是必须的。


??? abstract "元素是全页面唯一的，用 id；否则，用 class"

    ??? failure "不要万不得已不用 id"

        1. 因为重复不报错
        2. 有忌讳，console 里 window.打出的所有单词都不行(window 已有的全局属性)   
        3. 可以写但是js无法找到，只能通过 document.getElementById('top')  

    ??? note "id 的作用："

        1. CSS 相关
        2. JS 相关
            
            > xxx.style.border = "1px solid red";

    ??? note "tabindex:"

        * 0 是最后一个
        * -1：不访问

    ??? note "element.style:"

        * white-space: nowrap;      //不换行  
        * overflow: hidden;         //溢出隐藏  
	    * text-overflow: ellipsis;  //有溢出变..., to:e

    !!! note "title: 完整的内容"