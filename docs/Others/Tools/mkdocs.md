# MkDocs作为个人笔记用

## 0. 路线：

* 1.a -> 1.b

    * 1.a
    * 1.b

        * [owf-learn-mkdocs](http://learn.openwaterfoundation.org/owf-learn-mkdocs/new-project/)
        * [官网](https://www.mkdocs.org/)
        * [中文翻译](https://mkdocs.zimoapps.com/)
        * [Mkdocs 配置和使用](https://www.xncoding.com/2020/03/01/tool/mkdocs.html)
        * [PyMdown](https://facelessuser.github.io/pymdown-extensions/)
 

## 2. Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.

## 3. 网站

* 模板 

    * [mkdocs教程](https://cyent.github.io/markdown-with-mkdocs-material/install/local/)
    * [Material模板](https://squidfunk.github.io/mkdocs-material/getting-started/)
    * [南开模板](https://www.nkdacs.com/tutorial/md-template/)
    * [不要香菜](http://www.nocilantro.cn/front_end/html/)
    * [机器学习](http://docs.sqdxwz.com/ai-note/)

## 4. 官网文档

### 4.1 Home

1. 帮助信息

        $ mkdocs -h
        $ mkdocs --help
        $ mkdocs build --help

* 安装

        $ pip install mkdocs

* 查看版本

        $ mkdocs --version

    或

        $ mkdocs -V

    或

        $ pip show mkdocs

* 升级

        $ pip install -U mkdocs

* 卸载

        $ pip uninstall mkdocs

* 服务器默认地址为 127.0.0.1:8000 ，如果端口被占用怎么办呢？

    当然也支持自定义地址，使用下面这命令：

        $ mkdocs serve --dev-addr=127.0.0.1:8888

    或

        $ mkdocs serve -a 127.0.0.1:9999

* 使用 mkdocs build --clean 可以在构建时清理一些残留资源。

* 创建项目

        $ mkdocs new my-project

* 在mkdocs.yml的同级目录中启动服务器：

        $ mkdocs serve

* mkdocs.yml 

    * site_name: initial heading (初始标题)

    * nav: titles of navigation items (导航项的标题)

        > in navigation menu

* Building the site (建立网站)

        $ mkdocs build

    > 创建一个新目录 site


### 4.2 编写文档

项目主页应命名为index

#### MkDocs includes some extensions

* Internal links

    * Linking to pages#header: [software#1-tools](../software/#1-tools)

    * Linking to images and media: ![图片名](图片地址)

* Meta-Data

### 6. Deploying your docs(部署文档)

* Project Pages

        $ mkdocs gh-deploy


## 5 mkdocs 教程 


### 5.x Admonition

??? note

    !!! note "note 换名字"

        * note
        * seealso

        ``` javascript
        let a
        console.log(a)
        ``` 

    !!! note ""
        删除标题的 note

    ??? note "这是可折叠 note"
        FAQs(常见问题) 或 次要内容

??? note "其他类型"

    !!! success

    !!! question

        * question
        * help
        * faq

    !!! failure

    !!! info
    
        * info
        * todo

    !!! tip

        * tip
        * important

    !!! abstract

        * summary
        * tldr

    !!! warning

    !!! bug

    !!! quote