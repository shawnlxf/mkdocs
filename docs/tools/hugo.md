网站：
* [hugo](https://gohugo.io/)
* <https://gohugo.io/hosting-and-deployment/hosting-on-github/>

* <http://nanshu.wang/post/2015-01-31/>
* <https://www.jianshu.com/p/f1b02e00f206>
* <https://blog.coderzh.com/2015/08/29/hugo/>
* <https://www.zhihu.com/question/266175192>
* <https://hugo.aiaide.com/>
* <https://segmentfault.com/a/1190000012975914>
* <http://www.pangpangda.cn/32376/>

* <https://cloud.tencent.com/developer/article/1326514>
* <https://kuang.netlify.app/blog/hugo.html>

1. Quick Start

        hugo new site quickstart
        hugo new post/my-first-post.md      // for even
        hugo server -D      //可以预览草稿
        (hugo server)       //可以预览非草稿
        hugo -D
    
2. 把hugo.exe放到安装目录下，并把目录加到PATH

        draft: true改为false
        Ctrl + P: config.toml
            baseURL = "https://(shawnlxf.github.io)/"     //地址改成GitHub Pages显示的网址
            languageCode = "zh-Hans"                    //汉字简体
            title = "Shawn"