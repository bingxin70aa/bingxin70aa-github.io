---
layout: post
title: Jekyll其实很简单
categories: rwd
description:  搭建个人博客似乎听起来不简单，通过github让Jekyll来帮助你快速上手，让你拥有个属于自己风格的网页吧！
keywords: SVG,动画,矢量图
permalink: /posts/:categories/:title.html
---


##### Jekyll是一个生成静态网页的工具。
> 搭建个人博客似乎听起来不简单，通过github让Jekyll来帮助你快速上手，让你拥有个完全属于自己风格的网页吧！

- **_config.yml** 保存配置的文件 。  
  
- **_layouts** 存放的是模板文件（HTML档）。  

- **_drafts** 存放的是未发布的文件。  

- **_posts** 存放的是已发布的文章，特别注意！！文章格式必须是xxxx(年份)-xx(月份)-xx(日期)-文件名，比如2018-01-05-笔记。  

- **_data** “关于”页面的相关链接。  

- 每个文件都有类似以下的格式: 
 **layout  : post** （页面样式） title: xxxxx （页面名字） category: tech （分类） 