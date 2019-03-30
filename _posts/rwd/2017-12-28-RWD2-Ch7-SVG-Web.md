---
layout: post
title: SVG，你意想不到的清晰有趣
categories: rwd
description:  总是在网站上放一些模糊不清的图片,看着那雪花质感很难受吧？使用SVG（Scalable Vector Graphics，可伸缩矢量图）可以帮到你 !
keywords: SVG,动画,矢量图
permalink: /posts/:categories/:title.html
---  

> 总是在网站上放一些模糊不清的图片,看着那雪花质感很难受吧？使用SVG（Scalable Vector Graphics，可伸缩矢量图）可以帮到你 !  
 SVG是响应式设计中十分重要的一项技术。它是一种不会过时的、能够轻松解决多屏幕分辨率问题的技术。

## 看一看、点一点不要钱
1. 先简单的来从网页中打开一张[SVG图片](http://wcy.nfu.edu.cn/wp-content/uploads/_site/wcy_logo.svg)（最好用Chrome打开），悄悄告诉你这是我们学院的logo。

![wenchuan_logo](/images/posts/web/wcy_logo_old.svg)  

  2.右键点击检查，你会发现是一大串代码！

![wc_logo_code](/images/posts/web/wc_logo_code.jpg)

## 认识SVG的根元素
SVG的根元素有width、height和viewbox属性。（该图目前只有两个属性）

```
<svg
   viewBox="0 0 118.05 119.98"
   width="100%">
```

这三个属性在SVG展示的时候都起到了十分重要的作用。

## 看这里最实用的：在 Web 页面中插入 SVG 
#### 1、 简单的 img 标签
  最直接的插入SVG图像的方式就是使用一个简单的img标签即可：
```
<img src="wcy_logo.svg" alt="Amazing line art of a scone" /> 
```
是不是so easy ~

#### 2、使用 object 标签
object标签是W3C推荐的用于装载非HTML内容的容器（可以在https://www.w3.org/TR/html5/embedded-content-0.html了解object的规范）。我们可以像下面这样利用它插入SVG：   

```
<object data="img/svgfile.svg" type="image/svg+xml">
 <span class="fallback-info">Your browser doesn't support SVG</
span>
</object> 
```
data和type属性其实只有一个是必须要的，但是建议都添加上。data属性是你链接SVG资源的方式。type属性描述了内容的MIME类型。在这个例子中，image/svg+xml是SVG的MIME类型（互联网媒体类型）。你也可以添加width和height属性，如果你想约束这个容器中的SVG
的大小。  

###### 通过object标签插入到页面的SVG可以被JavaScript访问，这是采用这种插入方式的一个重要理由。
  
#### 3、把 SVG 作为背景图像插入
SVG可以在CSS中用作一个背景图像，和其他图片格式（PNG、JPG、GIF）一样。引入SVG
时并没有什么特别之处：
```
.item {
 background-image: url('image.svg');
} 
```

#### 4、内联 SVG
由于SVG仅仅是一个XML文档，所以你可以直接将它插入到HTML中。因为wc_log的代码比较长，所以直接在Chrome右键查看源代码，这里就不赘述啦。




更多请看，推荐网站：https://icomoon.io/