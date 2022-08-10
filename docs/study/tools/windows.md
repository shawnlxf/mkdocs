## 1. 推荐软件

??? note "普通软件"

    * 推荐：everything, typora
    * 词典：有道词典
    * pdf：WPS
    * 图示：亿图图示 edraw-max
    * 取色软件: Snipaste
    * gif: ScreenToGif, GifCam, LICEcap
    * 图片转换器(图片批量转换)
    * 迅捷压缩
    * 编辑： notepad++

        > 主题：solarized

    * 浏览器： firefox, opera


## 2. windows 10

!!! note "快捷键"

    * 投影：Win + P
    * 显示桌面：Win + D (再按又会回到之前的界面)

!!! question "睡眠"

    Win + X 调出常用菜单 -> 对应按键

??? question "win10 c盘多大合适"

    > 来源：百度，微信读书

    * 倘若大家的硬盘容量足够大，可以分80G-128G(如果有能力的话，建议直接单独一个128G固态用作系统安装)。

??? question "win10 c盘满了怎么清理"

    > [装机之家](http://www.lotpc.com/dnzs/9443.html)

    * 右键点击开始菜单（左键点击也能找到设置） -> 设置（Win + i） -> 系统 -> 存储 -> 临时文件 -> 删除文件
    * 右键点击C盘 -> 属性 -> 磁盘清理 -> 清理系统文件
    * 修改第三方软件的缓存文件路径（例如QQ或微信，特别重要）；如果你的电脑中有PS、PR等专业性软件，设置暂存盘为其它盘符，例如D盘、E盘、F盘等。

    ??? note "桌面路径和我的文档更改为其它盘符"
    
        * 右键点击“桌面” -> 属性 -> 位置 -> 将C:\Users\Administrator\Desktop的路径修改为D:\Users\Administrator\Desktop
        * 位置（方法同上） -> 移动 -> 选择D盘中新建的“桌面”文件夹 -> 应用
        * 右键点击开始菜单 -> 系统 -> 存储 -> 更改新内容的保存位置

    * 右键点击开始菜单 -> 系统 -> 相关设置：系统信息 -> 高级系统设置
    * 删除C盘的第三方软件：右键点击开始菜单 -> 设置 -> 系统 -> 存储 -> 应用和功能，安装到其他盘
    * 查看 -> 勾选【隐藏的项目】


??? question "win10 c盘 扩容"

    * 分区助手
    * 傲梅

    1. 进入磁盘管理
    2. 在主界面中找到与您想要扩展的分区相邻右侧的分区（比如您想扩展C分区，那么请您找到与之相邻右侧的分区），右键单击并选择“删除卷”。（或压缩卷）
    3. 右键单击您想要扩展的C分区，选择“扩展卷”

??? question "弹出USB大容量存储设备时出问题“该设备正在使用中”"

    1. 开始菜单右键 -> 事件查看器
    2. 自定义视图 -> 管理事件
    3. 再弹出一次移动硬盘
    4. 刷新事件(按F5) -> 点击第一条
    5. 下方 常规 -> 找到阻止弹出移动硬盘的程序（或进程ID）
    6. 合理的关掉这个程序

        > 打开任务管理器 -> 性能 -> 打开资源监视器 -> CPU -> 关联的句柄 -> 输入占用的进程ID -> 鼠标右键结束进程（DELETE键结束进程？） -> 再次弹出

??? question "如何设置.txt 的默认打开方式为 notepad++"

    > 在电脑 按文件类型设置默认应用 中 .txt 文件后的选项中没有 notepad++ 的情况下：

    1. 打开 notepad++ 软件
    2. 点击 设置 -> 首选项
    3. 选择 文件关联 -> notepad -> .txt -> "->" -> 关闭

??? question "虚拟内存"

    C盘还是D盘？多大？

??? question "开机启动项设置禁用"

    1. 开始菜单或任务栏上右键单击 -> 选中 任务管理器 -> 启动
    2. 选中应用，右键单击 -> 禁用 或 点击右下角“禁用”按钮


## 3. vscode

!!! note ""

    * 更换主题：文件 -> 首选项 -> 颜色主题

## Firefox

??? note "[创建，管理书签](https://support.mozilla.org/zh-CN/kb/%E5%88%9B%E5%BB%BA%EF%BC%8C%E7%AE%A1%E7%90%86%E4%B9%A6%E7%AD%BE)"

    您也可以使用键盘快捷键 Ctrl + Shift + D 来添加所有打开的标签页为书签。 

## 4. vpn

??? note "[freefq](https://github.com/freefq/free)"

    * github 搜索 翻墙，按最近更新时间排序。看 freefq，因为有免费节点。
    * github 找免费节点、机场、你懂的网站：搜 free，免费节点(Recently updated)，最新网址
    * chrome插件: "GitHub加速"，试了一次反而上不了github，可能哪里配置不对。

* [自由门](https://dongtaiwang.com/loc/mobile/?pm=y)
* [玛瑙云免费加速器](https://manaocloud.xyz)
* 789vpn

!!! question "vpn授权时无法点击“确定”按键"

    [如果本机已启用护眼模式、屏幕色温调节类等功能时，则需要在系统设置中结束该应用或者关闭该模式，然后重启腾讯加速器进行加速](https://support.qq.com/products/46125/faqs/51162?)


## 5. Mira

* vscode 颜色主题: Solarized Light
* 输入法：字号：36；皮肤自定义：灰色，黑色

??? note "站立时的保护套"

    ![][mira]

* 反向供电



  [mira]: windows-images/mira.png