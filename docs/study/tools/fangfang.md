    
## 杂项

* ~ 用户目录：C:\Users\18384
* 桌面：~/Desktop
* cat 输出完整内容，less 可以分页查看
* shebang: 如果你加了 shebang，删掉sh也能执行
* hosts 文件在哪？

    > C:\Windows\System32\drivers\etc\hosts
    >
    > /etc/hosts (macOS / Linux)

* `$ apt-get update`
* 正则表达式：\\[\d+\\]

??? note "tldr"

    ```
    $ npm i -g tldr
    $ yarn global add tldr
    ```

??? note "完整的 meta:vp (移动端适配)"

    > 修改 vscode 默认生成的 meta:vp
    >
    > [英文教程](https://code.visualstudio.com/docs/editor/emmet#_using-custom-emmet-snippets)

    ``` html
    <meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0, maximum-scale=1.0, user-scalable=no">
    ```

    淘宝手机版，右键 -> Copy -> Copy outerHTML

??? note "脑图："	  

    * 请使用 Mindjet MindManager 打开
    * 另外推荐一款脑图工具 XMind Zen，可以无限期试用。
    * Mindjet 和 XMind 用来做脑图都不错。

## 快捷键/node.js

* [方方 软件安装详解](https://xiedaimala.com/tasks/3722c995-fac6-444a-8d6e-6bfc8cf7cc1d)
* [Separate Window](https://xiedaimala.com/tasks/158827ba-7132-4983-b30f-6dd23ec03bdb)
* everything: 找到文件 -> 右键 -> 复制完整路径和文件名
* [命令行入门](https://xiedaimala.com/tasks/29aeec49-5e38-4730-bdc8-a0d568f67c1e) | [Use Cmder Embedded Git in VSCode](https://github.com/cmderdev/cmder/wiki/Seamless-VS-Code-Integration#use-cmder-embedded-git-in-vscode)

??? note "打印"

    * 边距：无  
    * 背景图形选上

??? note "常用快捷键"

    * Win组合键
    
        * win + Desktop：展示桌面
        * win + 方向键：移动窗口
        * alt + tab：切换窗口
        * win + tab：切换窗口，不常用
        * win + ctrl + 方向键：切换桌面
    
    * Ctrl组合键
    
        * ctrl + All / ctrl + Copy / ctrl + V / ctrl + Z / ctrl + Y
        * ctrl + Reload（F5）：刷新
        * ctrl + P：打印
  
!!! note "安装目录D:\Software: cmder, node.js, yarn"

??? abstract "命令行：cmder"

    ??? note "安装"

        * cmder.zip：

            > 右键->属性，勾选解除锁定       

    ??? note "配置"

        * 通用:

            * 最小化/恢复：Alt + `
            * 配色：Babun
            * Support special hotkeys                    

        * 字体:

            * 大小：18

        * 大小&位置:

            * 窗口大小：最大化

        * Quake风格：

            * 始终在顶层
    
        * 启动：

            * {bash::bash}

        * 环境：

            * set LANG=zh_CN.UTF-8

        * 按键&宏：

            * 分屏，右边：Alt + L
            * 分屏，底部：Alt + K

        * cmder here 在当前目录打开
        
            * <https://www.jianshu.com/p/552b7f0bb18c>
            * <https://blog.51cto.com/13853366/2352632>

    ??? note "快捷键"

        * Ctrl + T：新开标签
        * Ctrl + W：关闭当前标签
        * Win + Alt + P：设置

??? abstract "编辑： vscode"

    > vscode每次只开一个目录

    ??? note "设置"

        * File: Auto Save: onFocusChange
        * 字体大小：18
        * Format On Save

            > 自动格式化代码，工作后关闭

        * Emmet: Trigger Expansion On Tab

            > 适合新人，可能让Tab无法打字，有问题就关掉

        * 字体：Fira Code 

            > 进入otf/，全选，右键安装

        * Menu Bar

            > toggle

    ??? note "插件"

        * Code Spell Checker
        * Git Easy
        * Chinese
        * vscode*icons
        * Markdown All in One
        * Prettier(for JS, CSS)
        * (图床：PicGo)
        * (Markdown Preview Enhanced)
        * 运行 html 文件: open in browser / Live Server / HTML Preview

    ??? note "快捷键"

        * ctrl + p：找文件
        * ctrl + shift + p：输命令
        * alt + 单击：多位置输入
        * ctrl + /：注释
        * 输入link:css 引入 css 样式文件，输入 script:src 引入 js


??? abstract "浏览器：chrome"

    ??? note "插件："

        * Dark Reader
        * uBlocker
        * Separate Window
        * Death To \_blank
        * json viewer

    ??? note "主题："

        * Morpheon Dark

    ??? note "常用快捷键："

        * 鼠标中键单击：打开或关闭
        * ctrl + T：新开标签
        * ctrl + shift + T：撤销关闭
        * ctrl + W：关闭当前标签
        * ctrl + Location：输入网址
        * alt + 左右：前进后退
        * alt + 回车：在新标签打开
        * shift + 回车：在新窗口打开
        * ctrl + shift + delete：删除历史浏览数据

    ??? note "chrome 开发者工具："

        * 按ESC新建控制台
        * Sources面板里保存代码片段（snippets）
        * Network: Preserve log、Disable cache




??? note "node.js（10.20.1）, yarn: 所有软件的安装路径最好不能有空格"

    * 安装双数版 x64.msi

        > 安装后有了 node命令（因为PATH）、npm命令、npx命令

        ```
        $ node --version
        $ npm --version
        $ npx --version
        ```

    * npm

        ```
        $ npm i -g nrm          // npm 安装 nrm   
        $ nrm --version
        $ nrm ls
        $ nrm use taobao        // npm 从淘宝下载东西
        
        $ npm i -g http-server  // 会显示全局安装的位置        
        $ which http-server     // 安装位置
        ```

    * yarn代替npm（bug少，速度快）

        ```
        $ yarn --version
        $ yarn config list      // yarn 也会用 npm 的淘宝源，查看 registery
        $ yarn config get registry
        $ yarn global add yrm   // yarn 安装 yrm，跟 nrm 对应, yarn resouce manager
        $ yrm ls
        $ yrm use taobao    // 强行设置一下，多余
        ( $ yarn global add http-server )       // 已经装过，不需要再装，两个会安装到不同的地方，有一个能用就行        
        ```

??? note "命令行复制粘贴"

    * 在 Windows 的 cmder 里

        1. 用鼠标选中文字即自动复制
        * 单击鼠标右键就是粘贴
        * Shift + Insert 也是粘贴

    * 在 Windows 的 Git Bash 里

        1. 用鼠标选中文字，然后右键 copy 就是复制
        * 用鼠标选中文字，然后按 ctrl + insert 也是复制
        * 点击鼠标中键就是粘贴
        * Shift + Insert 也是粘贴
        

        
        


## 1 命令行：文件的增删改查

1. 查：

    * 目录：pwd, ls
    * 文件：cat, head, tail, less

2. 增：

    * 目录：mkdir

        ```
        $ mkdir -p a/b/c a/d/c
        ```

    * 文件：touch, echo, cp

        ```
        $ touch 1.txt 2.txt
        ```

        ```
        $ echo -e "haha\nhehe" > 4.txt
        ```

3. 删：rm

4. 其他：

    ```
    $ ls --help | less
    ```

    ```
    $ echo $?
    ```

## 2 &&, ;

* &&

    > 当一条命令成功之后，执行另一条

* ;

    > 不管成功失败，都执行另一条


## 3 git 本地仓库

* 本地仓就是 git init 创建的那个 .git 目录
* 老师为什么推崇使用 git commit -v ? 1. 这个命令可以帮助我们回顾改了些什么; 2. 这个命令可以促使我们写出更长的提交理由
* git branch x 的作用: 会基于本地仓库里最新一次 commit（提交），创建一个新的分支 x
* 运行 reset 命令前，一定要确保重要代码已经提交（commit）了，否则后悔莫及

??? note "git配置："

    ```
    git config --global user.name 你的英文名
    git config --global user.email 你的邮箱
    git config --global push.default simple
    git config --global core.quotepath false
    git config --global core.editor "code --wait"
    git config --global core.autocrlf input
    ```

    ```
    $ git config --global --list
    ```

    !!! note "注意：上面的英文名和邮箱跟 GitHub 没有关系。可以跟 GitHub 的用户名和邮箱保持一致，也可以不一致。我的是一致的。"


??? note "git常用命令："

    * .git目录就是本地仓库  
    
        * 它不会重复复制相同的文件（优化）  
        * 它可以支持多个分支

    ```
    $ git init                    //创建.git目录
    $ git add 路径
    $ git commit -m 字符串         //提交，并说明提交理由
                                  //如果字符串里有空格就要用引号包起来
    $ git commit -v
    ```

    ```
    git log
    git reflog
    git reset --hard xxxxxx     //切换版本
                                //reset会使本地未commit的改动消失
    git branch x                //基于当前commit创建一个新的分支
    git checkout x              //切换到另一个分支
                                //当前目录有未提交的代码，只要跟另一个分支不冲突，就不需要理会
    ```

    ```
    git stash                   //通灵术，如果上面的情况冲突了使用，也可以合并冲突
    git merge x                 //将另一个分支合并到当前分支
                                //可能有冲突，也可能没冲突
    ```

    ```
    git status 
    git status -sb              //查看哪些文件冲突了
                                //解决冲突 -> git add -> git status -sb -> 重复... -> git commit(不需要选项)
    git branch -d x             //删除分支
    ```

## 4 git远程仓库GitHub

??? note "GitHub"

    ![Github][Github]

??? note "ssh key 验证身份"

    上传代码是用私钥加密的，GitHub用公钥解密。如果解开了，说明是配对的。
    
    * 公钥: GitHub账号  
    * 私钥: 我的电脑
    
    !!! note "HTTPS协议需要每次都输入密码"

??? question "如何生成ssh key："

    > [GitHub帮助](https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

    ```
    ssh-keygen -t rsa -b 4096 -C 你的邮箱
    //然后一直回车，直到没有提示

    cat ~/.ssh/id_rsa.pub       //得到公钥内容
    ssh -T git@github.com       //回答yes并回车
    ```

!!! abstract "常用命令"

    ??? note "git clone: 是在我没有代码的前提下，下载整个仓库到本地"

        1. `git clone git@?/xxx.git`
        2. `git clone git@?/xxx.git yyy`
        3. `git clone git@?/xxx.git .    //不会新建目录`

        > [git clone满速下载教程](https://jscode.me/t/topic/789)

    !!! note "git pull: 是在我已经拥有本地仓库的前提下，只下载本地没有的那一部分变更"

    ??? note "git push"

        ```
        git commit  
        git commit -v --amend

        git remote add origin git@github.com:shawnlxf/demo-1.git
        //在本地添加远程仓库的地址
        //origin是远程仓库的默认名字，可以换，建议不要换

        git push -u origin master
        //推送本地master分支到远程origin的master分支
        //-u origin master的意思是设置上游分支，之后就不用再设置了
        ```

??? question "上传到两个远程仓库"

    ```
    git remote add repo2 git@xxxxxx
    git push -u repo2 master
    ```

??? question "如何上传其他分支："

    * 方法1：

        ```
        $ git push origin x:x
        ```

    * 方法2：

        ```
        $ git checkout x
        $ git push -u origin x
        ```

??? note "杂项"

    * GitHub用来备份.git/而已

    * `$ yarn global add git-open`

        > 用 git open 打开GitHub远程仓库首页

    ??? question "如何下载某个分支："

        * 先下载整个仓库，然后git checkout分支名
        * 或者搜命令



    ??? note "国内的代替品"

        * coding.net (腾讯战略投资)
        * gitlab.com
        * 码云 gitee.com (开源中国)

    ??? note "远程仓库"

        1. 只是本地仓库的备份，所以变化都要先commit到本地仓库，然后push到远程
        2. 无法下载部分代码，只能clone整个仓库

```
git pull
git pull repo2 master:x

git remote -v
git remote remove origin2

yarn global add git-open
```

??? note "高级操作："

    ```
    touch ~/.bashrc
    echo 'alias ga="git add"'>> ~/.bashrc
    echo 'alias gc="git commit -v"'>> ~/.bashrc
    echo 'alias gl="git pull"'>> ~/.bashrc
    echo 'alias gp="git push"'>> ~/.bashrc
    echo 'alias gco="git checkout"'>> ~/.bashrc
    echo 'alias gst="git status -sb"'>> ~/.bashrc
    ```

??? note "好看的glog:"

    1. 最后 code ~/.bashrc 在文件最后加上 

        ```
        alias glog="git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit -- | less"
        ```

    2. 重启命令行，或者运行 source ~/.bashrc

??? note "美化历史命令"

    ```
    git rebase -i xxxx
    ```

    ![Git Rebase][Git Rebase]

    ??? question "出错怎么办："

        * 看log提示
        * 中止

            ```
            git rebase --abort 可以取消rebase
            ```

        * 继续
  
            ```
            git rebase --continue 可以继续
            ```

??? note "通灵术"
    
    > 不想提交代码，又不想删除代码，那可以找个空间把代码临时藏起来

    git stash / git stash pop

??? note "github pages"

    1. github新建仓库: shawnlxf.github.io
    2. 上传之后进入仓库settings, GitHub Pages -> Source -> master branch 
    3. 把public外的目录上传到github，如果添加远程仓库出错

        ```
        $ git remote set-url origin git@xxxxxx
        ```

  [Github]: fangfang-images/github.png
  [Git Rebase]: fangfang-images/git-rebase.png

## 5 markdown

* GitHub直接预览markdown
* 文件后缀.md 或 .markdown

??? note "markdown 语法"

    [其他标题语法](https://markdown-zh.readthedocs.io/en/latest/blockelements/#header)

    ![Markdown][Markdown]

  [Markdown]: fangfang-images/markdown.png
  


    