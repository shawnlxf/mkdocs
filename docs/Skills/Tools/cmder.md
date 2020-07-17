1. bash 快捷键

    Alt + Backspace: 删除前一个单词
    Shift + Insert: 向终端内粘贴文本
    Ctrl + C：中断终端中正在执行的任务。
    Ctrl + Z：使正在运行在终端的任务，运行于后台。 （可用fg恢复）
    Ctrl + D: 在空命令行的情况下可以退出终端。
    Ctrl + L: 清空终端

2.  编辑命令

    Ctrl + a ：移到命令行首 (ahead)
    Ctrl + e ：移到命令行尾 (end)
    Ctrl + f ：按字符前移（右向）
    Ctrl + b ：按字符后移（左向）
    Alt + f ：按单词前移（右向）
    Alt + b ：按单词后移（左向）
    Ctrl + xx：在命令行首和光标之间移动
    Ctrl + u ：从光标处删除至命令行首
    Ctrl + k ：从光标处删除至命令行尾
    Ctrl + w ：从光标处删除至字首
    Alt + d ：从光标处删除至字尾
    Ctrl + d ：删除光标处的字符
    Ctrl + h ：删除光标前的字符
    Ctrl + y ：粘贴至光标后 (U, K, W相关)
    Alt + c ：从光标处更改为首字母大写的单词
    Alt + u ：从光标处更改为全部大写的单词
    Alt + l ：从光标处更改为全部小写的单词
    Ctrl + t ：交换光标处和之前的字符
    Alt + t ：交换光标处和之前的单词
    Alt + Backspace：与 Ctrl + w ~~相同~~类似，分隔符有些差别 [感谢 rezilla 指正]

重新执行命令

    Ctrl + r：逆向搜索命令历史
    Ctrl + g：从历史搜索模式退出
    Ctrl + p：历史中的上一条命令
    Ctrl + n：历史中的下一条命令
    Alt + .：使用上一条命令的最后一个参数

控制命令

    Ctrl + l：清屏
    Ctrl + o：执行当前命令，并选择上一条命令
    Ctrl + s：阻止屏幕输出
    Ctrl + q：允许屏幕输出
    Ctrl + c：终止命令
    Ctrl + z：挂起命令

Bang (!) 命令

    !!：执行上一条命令
    !blah：执行最近的以 blah 开头的命令，如 !ls
    !blah:p：仅打印输出，而不执行
    !$：上一条命令的最后一个参数，与 Alt + . 相同
    !$:p：打印输出 !$ 的内容
    !*：上一条命令的所有参数
    !*:p：打印输出 !* 的内容
    ^blah：删除上一条命令中的 blah
    ^blah^foo：将上一条命令中的 blah 替换为 foo
    ^blah^foo^：将上一条命令中所有的 blah 都替换为 foo
