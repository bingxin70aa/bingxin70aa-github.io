
## bing xin
我的个人博客在这里：[https://bingxin70aa.github.io](https://bingxin70aa.github.io)

### 概览

<!-- vim-markdown-toc GFM -->

* [Fork 后该干什么？](#Fork-后该干什么？)
* [贴心提示](#贴心提示)
* [经验与思考](#经验与思考)
* [致谢](#致谢)

<!-- vim-markdown-toc GFM -->

### Fork 后该干什么？

Fork 此项目后，还是 bing xin 的页面？ 需要做一些简单的修改才能让“你的博客”真正的跑起来！


1. **更改项目的名称与分支** ( Github 的 Settings 中 )

    ① 将项目命名为“username.github.io”，分支为“master branch”。
    
    ② 将项目命名为其他名称也可以自动生成 Github Pages 页面
    
1. **修改域名**  

      如果你需要绑定自己的域名，那么新建文件 CNAME 并写上您对应的域名（注意不需要添加https://)；如果不需要绑定自己的域名，那么忽略该条建议。
    
1. **修改配置** ！！

      网站的主要配置都在 \_config.yml文件中，将其当中的 url、title、gitalk等等修改为自己的内容。  
      
    **评论模块：** 目前支持 disqus、gitment 和 gitalk，选用其中一种就可以了，推荐使用 gitalk。它们各自的配置指南链接在 \_config.yml 文件的 Comments 一节里都贴出来了。

1. **删除 bing xin 的杂物**
 
    文章部分，除了 template.md 文件外，都可以全部删除，然后添加你自己的内容。

    页面“关于”中的内容也可以删除填上个人信息，包括 \_data 目录下的 skills.yml 和 social.yml 文件里的数据。  

    如对项目中文件存放内容不清楚，可[参见此处](https://bingxin70aa.github.io//posts/rwd/web-jeklly.html)。
    
### 致谢
本博客外观根据[mzlogin](http://mazhuang.org)修改，非常感谢。
