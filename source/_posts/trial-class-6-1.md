---
title: Jser 第八期训练营
date: 2020-06-01 19:04:32
tags:
description: 2020年暑期正式营开始纳新啦
---

### 机会都是留给有准备的人

---

#### 大学中与编程相关的比赛列表

- 数学建模
  - 美赛：每年的 1 月底到 2 月之间，比赛时间 96 小时，每年的 4 月公布结果。
  - 省赛校赛：比赛时间每年 4-5 月，比赛时间一个月，每年的 6 到 7 月之间公布结果。（今年推迟到 6 月比赛）
  - 挑战杯：每年 4 月，比赛时间 4 天，5 月末公布结果（今年推迟到 5 月末比赛）
  - 中青杯：每年 5 月末或 6 月初，比赛时间 3 天，7 月公布结果。
  - 国赛：每年的 9 月初，比赛时间 72 小时，每年的 11 到 12 月之间公布结果。
  - 亚太赛：每年 11 到 12 月比赛，比赛时间 96 小时，1 月公布结果。
- SIPT：校级/院级 每年 11 月立项，5 月中期检查，评定校级立项还是院级立项，次年 11 月左右结题。
- 三创赛：校级/省级/国家级
  - 校赛： 5 月
  - 省赛： 6 月
  - 国赛： 11 月
- 互联网+创新创业：校级/省级/国家级
  - 校赛： 5 月
  - 省赛： 9 月

机会其实很多，怎么把握住机会很重要！
等到考试报名的时候才知道自己没有编程基础就晚了

### 训练营本次内容展示

---

#### 弹跳动画

{% asset_img 弹跳动画.gif 弹跳动画 %}

#### 满屏爱心

{% asset_img 满屏爱心.gif 满屏爱心 %}

#### Excel 表格的自动化处理

{% asset_img 表格自动化处理.gif 表格自动化处理 %}

#### 爬虫 -- 爬取某一订阅号的全部图文

{% asset_img 获取公众号·网络爬虫.gif 获取公众号·网络爬虫 %}

### 正式开始 - 网站开发

---

#### 网站页面的基本组成

我们<span style='cursor:pointer;' onclick='clickAnswer1()'>平时</span>看到的网页是由 HTML、CSS、JavaScript 组成的，他们三个有不同的分工，HTML 负责呈现页面的基本内容，比如文字、图片、音频、视频都是由 HTML 负责呈现的；
但是为什么我们的图片会居中显示呢？字体为什么有的大有的小呢？为什么有的加粗有的正常呢？字体的样式由什么来控制呢？
事实上，CSS 就是控制 HTML 以什么样子显示的；
而网页中一般都存在几个按钮或者可以点击的图片，点击这些按钮或者图片之后的行为就是由 Javascript 来定义的。

#### 小程序、App

小程序: 另一种前端，其实只是标签改变了，学会任何一个都能上手另外一个。
App: App 的生态比较复杂，说个很简单就能实现的。只是编写一个 app 的外壳，其余内容都是网页；

**① 提问：假如一个开发者某天(日期设为 A)开发了一个手机页面，过了一个月以后，这个开发者开发过程中发现了一个业务逻辑和日期 A 开发的网页差不多的网页；问：是重新写一个效率更高还是把之前的复制过来效率更高？**

<div style='display:none;color: #c00;font-weight: bolder;' id='answer1'>答：无悬念，当然是复制过来效率更高</div>

**② 提问：一天，小明准备写一个类似有赞的商城；问：小明可不可以去有赞商城的网页复制源码？**

<div style='display:none;color: #c00;font-weight: bolder;' id='answer2'>
    答：其实可以，但是会比自己重新写更复杂，因为我们需要去理解有赞商城开发者的思路。而我觉得编程最大的魅力就是思路是千变万化的；也就是网页能做成什么样子其实更多的看个人的想象力。
    而我们有更简单的方式去实现一个有赞商城(拿小程序举例)，点击进入以下网页<a href='https://youzan.github.io/vant-weapp/#/intro'>ZanUI - 再造一个有赞微商城也不在话下</a>
</div>

<script>
function clickAnswer1() {
    var answer1 = document.querySelector('#answer1')
    if(answer1.style.display == 'none'){
        answer1.style.display = 'block'
    }else{
       answer1.style.display = 'none' 
    }
}
document.addEventListener('keyup',function(e){
    console.log(e)
    if(e.key === '~'){
        var answer2 = document.querySelector('#answer2')
        if(answer2.style.display == 'none'){
            answer2.style.display = 'block'
        }else{
           answer2.style.display = 'none' 
        }
    }
})
</script>

#### 网页、小程序当前的生态环境

正如上面所说，前端开发的生态环境已经相当完善，除了手机端的有赞小程序 UI 组件；还有[手机端有赞网页 UI 组件](https://youzan.github.io/vant/#/zh-CN/)、[PC 端饿了么网页 UI 组件](https://element.eleme.cn/#/zh-CN/component/installation)

所以前端开发已经很“接地气了”，把前端的三大基础学好就可以使用这些非常方便的 UI 组件；

#### 基本的 HTML 结构

每个网页都有一个基本结构，用来承载页面内容。

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

##### 引入 CSS 与 JS 的方式

前端网页的基本组成结构包括 HTML、CSS、Js，至此我们已经知道该如何书写 HTML，那么我们应该如何在代码中加入 CSS 与 JS 呢？

---

```html
<!-- 在HTML中插入CSS的方式有三种 -->
<link rel="stylesheet" href="./index.css" />
<!-- rel:规定当前文档与被链接文档之间的关系。href:规定被链接文档的位置。 -->

<!-- 在HTML中插入JS的方式有两种 -->
<script src="./index.js"></script>
<!-- src:规定被链接文档的位置。 -->
```

_'./'这种字段称为“相对路径”；路径的概念小白可能不太好理解，其实这个“路径”相当于一个地址，类似于我们在电脑上播放本地视频，需要打开指定文件，这个相对路径就是文件的地址_

### 第一个项目：弹跳动画

---

{% asset_img 弹跳动画.gif 弹跳动画 %}

#### ① 先建立 HTML 的基本结构

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
    hello world
  </body>
</html>
```

#### ② 在页面中加入需要跳动的方块

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
    <div class="box"></div>
  </body>
</html>
```
