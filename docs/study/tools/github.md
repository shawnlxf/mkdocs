* [GitHub pages CNAME file](https://help.github.com/en/github/working-with-github-pages/configuring-a-custom-domain-for-your-github-pages-site)

??? summary "[GitHub Docs](https://docs.github.com/en)"

    * Authentication
        * Connecting to GitHub with SSH

??? question "git push 失败"

    ??? quote "[参考](https://www.v2ex.com/t/841032)"

        * [一文让你了解如何为 Git 设置代理](https://ericclose.github.io/git-proxy-config.html)
        * [Correct way to set git proxy](https://www.wuyiting.cn/blog/Correct%20way%20to%20set%20git%20proxy)

    ??? info "1"

        ![][ssh-problem-1]
        ![][ssh-problem-2]

        ## 解决方法

        创建 ~/.ssh/config 文件，添加

        ```
        Host github.com
            User git
            ProxyCommand connect -H 127.0.0.1:8580 %h %p
        ```

    ??? info "2"

        ![][ssh-problem-3]

        ## 解决方法

        删除并生成新的 SSH key


??? question "如何使用 GitHub Pages 预览 HTML"

    !!! quote "[GitHub帮助](https://help.github.com/cn/github/working-with-github-pages/creating-a-github-pages-site)"

    > GitHub Pages 是一项静态站点托管服务，在上面可以预览HTML页面。

    ## 步骤

    1. 新建仓库，如果您创建的是用户或组织站点，仓库名称必须为 <user\>.github.io 或 <organization\>.github.io。
    2. 上传代码到该仓库。
    3. 在仓库名称下，单击Settings（设置）。
    4. 在“GitHub Pages”下，使用 Source（源）下拉菜单选择发布源（如master branch）。
    5. 要查看您已发布的站点，请在“GitHub Pages”下点击您的站点 URL。

    ![Github Pages][Github Pages]

  [Github Pages]: github-images/github-pages.png
  [ssh-problem-1]: github-images/ssh-problem-1.png
  [ssh-problem-2]: github-images/ssh-problem-2.png
  [ssh-problem-3]: github-images/ssh-problem-3.png