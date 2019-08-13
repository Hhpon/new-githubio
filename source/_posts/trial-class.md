---
title: Jser 试听课
date: 2019-08-13 09:58:11
tags:
---

### 试听课内容 - 个人名片
***

#### 个人名片

[个人名片预览地址](http://jser.hhp.im/trial/hhp/)

{% asset_img 2.jpg 300 %}

#### 网站所需资源

{% asset_img 1.png 100 %}
{% asset_img 2.png 100 %}
{% asset_img 3.png 50 %}
{% asset_img 4.png 50 %}

### 正式开始 - 网站开发
***

#### 网站页面的基本组成

我们平时看到的网页是由 HTML、CSS、JavaScript 组成的，他们三个有不同的分工，HTML 负责呈现页面的基本内容，比如文字、图片、音频、视频都是由 HTML 负责呈现的；
但是为什么我们的图片会居中显示呢？字体为什么有的大有的小呢？为什么有的加粗有的正常呢？字体的样式由什么来控制呢？
事实上，CSS 就是控制 HTML 以什么样子显示的；
而网页中一般都存在几个按钮或者可以点击的图片，点击这些按钮或者图片之后的行为就是由 Javascript 来定义的。

#### 基本的 HTML 结构

每个网页都有一个基本结构，用来承载页面内容

**基本结构**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Document</title>
  </head>
  <body>
    <div>
      hello world
    </div>
  </body>
</html>
```

由于我们在写代码的时候有很多这样的基本结构，所以编辑器(我们用来写代码的东西)给我们提供了很多快捷键，我们来试一下页面的基本结构。

##### HTML 的重要概念 - 标签

我们看基本结构里面这些用尖括号括起来的东西是什么啊？我们把这些以尖括号开始并且以尖括号结束的代码称为**标签**。

```html
<!-- 我们都是标签 -->
<html></html>
<head></head>
<body></body>
<meta />
<header></header>
<footer></footer>
<h2></h2>
<h3></h3>
<h4></h4>
<h6></h6>
<!-- 下方是一会主要用到的 -->
<div></div>
<img />
<h1></h1>
<h5></h5>
```

成对的标签编辑器给我们也提供了快捷键

#### 完成页面的基本内容

##### 第一步引入图片

图片的引入我们要使用 img 标签

src 规定显示图像的 URL
alt 规定图像的替换文本

```html
<!-- 引入网络图片 -->
<img src="https://hhpon.github.io/2018/12/15/Jser-trial-class/2.png" />
<!-- 引入本地图片 -->
<img src="./touxiang.jpg" />
```

而图片的大小我们使用宽度和高度来控制

height 规定图片高度
width 规定图片宽度

```html
<!-- 重点记忆，一会我们给盒子设置宽度和高度的时候方法不一样 -->
<img
  src="https://hhpon.github.io/2018/12/15/Jser-trial-class/2.png"
  height="50px"
/>
```

我们在构建网页的基本内容的时候可以使用 div 包裹住我们的图片，文字等。

这种布局方式是我个人在开发过程中养成的习惯，并不是最好的方法，方法还有很多。

到这里为止，页面上的图片我们都放进网页里面啦。

##### 第二步增加网页文字

1. 网页文字的引入方法比较多，首先我们可以直接写在 div 标签里面
2. 对于希望强调类的文字 HTML 提供给我们了 h1-h6 的标签

```html
<h1>安德鲁</h1>
<h5>东北农业大学·工程学院</h5>
<h5>2014级</h5>
```

到此为止页面的基本内容我们已经构建完毕了。

#### 规定网页内容的显示样式

和我们要完成的网页对比，我们就剩下一些排版了，比如让头像居中，让文字居中等。

##### 给标签添加 CSS 样式的方法

```html
<div style="css具体内容">hello world</div>
```

##### 图片文字居中的方法

```html
<!-- text-align 规定文本水平对齐方式 -->
<div style="text-align: center;">
  因为个人兴趣，我一直希望制作一个自己的app，也希望可以交到更多的朋友。
</div>
```

##### 上下间距调节的方法

```html
<!-- margin 规定元素的外边距 -->
<div style="text-align: center;margin: 10px;">
  因为个人兴趣，我一直希望制作一个自己的app，也希望可以交到更多的朋友。
</div>
```

今天重点介绍一下 margin 这个属性，margin 在这里是外边距的意思，margin: 10px;的意思即为外边距为10px;