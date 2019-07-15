---
title: HTML/CSS 入门
date: 2019-07-15 14:02:40
tags:
---

### HTML 入门

***

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

#### HTML 重要概念 —— 标签

我们可以看到很多由尖括号包围的关键词组成了页面的基本结构，他们我们称之为标签。HTML 就是通过标签来描述网页的。

**HTML 里面有两类主要的标签，分别是div、span**

```html
<div>1</div>
<div>2</div>
<div>3</div>
<span>4</span>
<span>5</span>
<span>6</span>
```

把这些代码嵌套在 HTML 基本结构的 body 标签里面，我们可以看到 div 类标签的内容会重启一行显示内容；而 span 则不会。

所以我们把具有这两类属性的标签分成两类；一类是块级元素，显示时会重启一行，一类是行内元素，显示不换行。(反过来是不对的)

##### 块级元素

除了 div 还有哪些块级元素呢？

```html
<h1> - <h6>
<p></p>
<ul></ul>
<ol></ol>
<header></header>
<footer></footer>
<article></article>
<section></section>
```

这些块级元素是为了语义化更加明显，比如 p 标签，代表段落，header 标签用于展示介绍性内容，footer 标签展示页脚。

**示例一**

```html
<ul>
    <li>h</li>
    <li>t</li>
    <li>m</li>
    <li>l</li>
</ul>

<h1>hello world</h1>
```

##### 行内元素

```html
<button></button>
<input />
<img />
```

### CSS 入门
***

在网页里面 HTML 主要负责显示内容，那么内容的具体样子呢？为什么有的字体大有的字体小？有的字体居左，有的字体居中？

HTML 显示的样式就是由 CSS 来负责的，那么我们如何引入 CSS 呢？

- 内部样式表
- 外部样式表
- 行内样式表

引入css一共有这三种引入方式，今天我要给大家介绍的就是这个内部样式表。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        .box {
            height: 100px;
            width: 100px;
            background-color: blue;
        }
    </style>
</head>

<body>
    <div class="box">1</div>
    <div>2</div>
</body>

</html>
```

这个 style 标签的写法就是内部样式表，大家把这段代码敲到文件里面看一下显示的样子？思考一个问题：为什么内容为1的盒子的样子与内容为2的盒子显示的结果不一样呢？

**到底是什么原因导致1盒子与内部样式表的 CSS 属性联系起来了呢？**

#### CSS 选择器

- ID 选择器
- 类选择器
- 元素选择器
- 通用选择器


##### ID 选择器

标签的ID是唯一的，就像我们的学号一样，每个人一定是不一样的。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        #box {
            height: 100px;
            width: 100px;
            background-color: blue;
        }
    </style>
</head>

<body>
    <div id="box">1</div>
    <div>2</div>
</body>

</html>
```


##### 类选择器

类选择器不同于ID选择器，可以不唯一

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        .box {
            height: 100px;
            width: 100px;
            background-color: blue;
        }
    </style>
</head>

<body>
    <div class="box">1</div>
    <div>2</div>
</body>

</html>
```

类选择器需要给指定标签添加 class 属性，并且指定与内部样式表内相应的内容相同的属性名字。

##### 标签选择器

字面意思，其实就是选择标签的

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        div {
            height: 100px;
            width: 100px;
            background-color: blue;
        }
    </style>
</head>

<body>
    <div>1</div>
    <div>2</div>
</body>

</html>
```

##### 通用选择器

通用：对所有都管用

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        * {
            margin: 0;
        }
    </style>
</head>

<body>
    <div>1</div>
    <div>2</div>
</body>

</html>
```

##### 选择器总结

这四种选择器为 CSS 中最基本的选择器，每种选择器之间仅有两个地方不一样，一个内部样式表里面的写法，一个是标签里面的写法，简单记忆一下。

**思考一个问题，如果我对于相同的标签设置了两个相同的选择器，选择器里面的内容不一样，那么显示的时候应该以谁为准呢？**

**思考一个新的问题，如果一个标签我既设置了 ID 选择器，又设置了 class 选择器，显示的时候又以谁为准呢？**

物以稀为贵，代码里面就是以稀少的为准了。

#### 组合器和选择器组

虽然一次使用一个选择器就很有用，但在某些情形中却可能导致效率低下。 CSS选择器在你开始组合他们时就进行细粒度选择的会更加有效。基于元素之间的相互关联关系，CSS提供了几种方法来对元素进行选择。下表使用连接符展示了这些关联关系(A和B代表前文所述的任意选择器):

{% asset_img 选择器组.png 选择器组 %}

**当你的项目复杂到一定程度，你可能会用到选择器组，那么到时候你一定不可避免的遇到选择器的优先级问题。**

[选择器优先级自由阅读](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Specificity)
