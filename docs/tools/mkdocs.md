# MkDocs作为个人笔记用
<http://www.imooc.com/article/295990>

<https://www.sunbufu.club/2019/01/14/GithubPages-CodingPages/>
<https://pushmind.org/2017/05/16/the-pit-of-mkdocs-in-traditional-field/#mathjax>
<https://yangfangs.github.io/2016/08/09/install-build-mkdocs/>

## 1. Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.
```
  $ mkdocs --help
  $ mkdocs build --help
```

## 2. Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.

## 3. 网站
[官网](https://www.mkdocs.org/)
[中文翻译](https://mkdocs.zimoapps.com/)

```
    $ mkdocs --version
```

## 4. 入门
```
    $ mkdocs new my-project
    $ cd my-project
```

在mkdocs.yml的同级目录中启动服务器：
```
    $ mkdocs serve
```

<http://127.0.0.1:8000/>

生成文档，创建一个名为site的新目录：
```
    $ mkdocs build
```

删除site目录中的旧文件：
```
    $mkdocs build --clean
```

## 5. 编写文档
项目主页应命名为index

### MkDocs includes some extensions

* Internal links

    * Linking to pages#header: [Home#3. 网站](../README.md#3)

    * Linking to images and media: ![RUNOOB 图标](../img/runoob-logo.png)

* Meta-Data

## 6. Deploying your docs(部署文档)
* Project Pages
    * $ mkdocs gh-deploy