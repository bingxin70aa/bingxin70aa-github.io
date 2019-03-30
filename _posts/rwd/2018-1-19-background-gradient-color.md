---
layout: post
title: 使用CSS background-image 属性更换首页背景为渐变色
categories: css
description:  单色系的背景好单调，尝试添加新的颜色进来丰富页面！
keywords: background,CSS 渐变,背景,颜色,首页,background-image
permalink: /posts/rwd/:title.html
---  


> 单色系的背景好单调，所以我尝试添加新的颜色,即渐变色来丰富页面！  
  
##   CSS background-image 属性  


实例：

```
body
  { 
  background-image: url(bgimage.gif);
  background-color: #000000;
  }
```


###  linear-gradient

  这里运用图像值 CSS Image Data Types 中的 **linear-gradient( )**，即用线性渐变创建图像 。 

- **linear-gradient( 度数deg ， 颜色1 ，颜色2 )**
  
  如果按照时钟来看其度数，九点为 0deg 、 十二点为 90deg 、三点为 180deg，以此类推。当度数为 0deg时，颜色1在下，颜色2在上。
```
body
  { 
  background-image: linear-gradient(90deg, #2580B3, #304352);
  }
```

效果如图：

![background_image_color](/images/posts/web/background_image_color.jpg)  

更多感兴趣的[属性](https://bingxin70aa.github.io//posts/blog/w3cschool.html)或[值](http://www.css88.com/book/css/values/image/index.htm)，请参见链接。