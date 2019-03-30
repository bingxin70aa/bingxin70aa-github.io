---
layout: post
title: Chrome控制台Console的用法
categories: rwd
description:  当你想要在网页上看到好看的图片，想要了解所有图片的位置，但是苦于不知来源时，你可以使用以下方法帮助自己。
keywords: Chrome,Console
permalink: /posts/:categories/:title.html
---  


## 检查网页上的图片
当你想要在网页上看到好看的图片，想要了解所有图片的位置，但是苦于不知来源时，你可以使用以下方法帮助自己。

#### 查找图片

- 点击Console
- 输入

```
('img')
```

------------------------------------

#### 查找文件名和档名

- 点击Console
- 输入

```
$('#js-menu > ul > li:nth-child(1) > a > img')
```
  将会生成

```
[ img.teaser ]
```
  即 [ 文件格式 . 档名 ] 

--------------------------------------------

#### 查找图片地址
- 点击Console
- 输入
```
$('#js-menu > ul >li:nth-child(1) > a >img')[0].src
```
将会生成

```
"https://luo00789.github.io/images/kuxing.jpg"
```
  即网页图片地址（以https://luo00789.github.io为例）
   
   