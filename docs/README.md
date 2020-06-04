# MkDocs作为个人笔记用

## 1. Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.
  $ mkdocs --help
  $ mkdocs build --help

## 2. Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.

## 3. 网站
[官网](https://www.mkdocs.org/)
[中文翻译](https://mkdocs.zimoapps.com/)

[知乎](https://zhuanlan.zhihu.com/p/61492480)
[少数派](https://sspai.com/post/47030)

    $ mkdocs --version

## 4. 入门
    $ mkdocs new my-project
    $ cd my-project

在mkdocs.yml的同级目录中启动服务器：

    $ mkdocs serve

<http://127.0.0.1:8000/>

生成文档，创建一个名为site的新目录：

    $ mkdocs build

删除site目录中的旧文件：

    $mkdocs build --clean

## 5. 编写文档
项目主页应命名为index

MkDocs includes some extensions

* Internal links

    * Linking to pages#header: [Home#3. 网站](README.md#3)

    * Linking to images and media: ![RUNOOB 图标](http://static.runoob.com/images/runoob-logo.png "RUNOOB")


