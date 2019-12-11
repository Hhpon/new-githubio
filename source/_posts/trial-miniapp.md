---
title: Jser训练营
date: 2019-10-16 19:47:34
tags:
hidden: true
---

### 认识小程序

---

#### 示例小程序的目录结构

一个小程序主体部分由三个文件组成，必须放在项目的根目录，如下：

{% asset_img main.png %}

app.js 会在小程序打开的时候执行一些初始化的操作，如声明变量之类
app.json 用来对微信小程序进行全局配置比如小程序的首页是什么，小程序页面的窗口表现，设置 tab 菜单栏
app.wxss 各个页面共用该页面的样式

一个小程序页面由四个文件组成，分别是：

{% asset_img page.png %}

### 第一个小程序作品

---

{% asset_img 2.jpg 300 %}

#### 所需资源

{% asset_img 1.png 200 %}
{% asset_img 2.png 100 %}
{% asset_img 3.png 50 %}
{% asset_img 4.png 30 %}

### Hello World

---

在 app.json 文件中创建新的页面路径

```json
{
  "pages": ["pages/main/main"]
}
```

微信开发者工具内找到 pages 文件夹，并在文件夹内新建 main 文件夹，在 main 文件夹内新建文件 main.wxml、main.wxss、main.js、main.json

打开 main.wxml 文件，在文件内输入如下内容

```html
<view>Hello World</view>
```

#### 小程序的基本组成

一个小程序页面是由四个文件组成的，wxml 负责呈现页面的基本内容，比如文字、图片、音频、视频这些都是由 HTML 来呈现的。
但是为什么我们的图片会居中显示呢?字体为什么有的大有的笑呢？为什么有的是斜体呢？那么这些是由什么来控制的呢？
事实上，wxss 就是用来控制 wxml 以什么样子显示的；
小程序中一般都会存在几个按钮或者可以点击的图片，点击这些按钮或者图片之后的动作就是由 Javascript 来定义的。

#### 重要概念 - 标签

我们回想一下刚刚 Hello World 的例子，那个用尖括号括起来的东西是什么？

**我们把这些以尖括号开始并且以尖括号结束的代码成为标签**

```html
<view></view>
<!--你的第一个小程序将要用到最多的标签-->
<image></image>
<!--引入图片的标签-->
<!--以上是需要在我们的小程序中将要用到的小程序，那么除了这些还有哪些小程序标签呢？-->
<text></text>
<button></button>
<video></video>
<audio></audio>
<map></map>
<icon></icon>
```

在大家初次写标签的时候很多人总是会把单词写错，这里告诉大家一个不容易出错的窍门，编辑器是有提示功能的，我们使用编辑器的提示功能会大大减少我们出错的可能。

小程序中还有很多标签等着你去发现哦~

#### 填充页面内容

##### 第一步了解 view 标签

试一下这个例子

```html
Hello World hello world
```

再试一下这个例子

```html
<view>Hello World</view> <view>Hello World</view>
```

**经过这两个例子我们可以发现，我们的 view 标签会让标签内容换行显示。这是一个重要特点，对于填充页面内容很重要！**

##### 第二步了解 image 标签

```html
<image
  src="https://jserclub.github.io/2019/08/13/trial-class/2.png"
  mode="widthFix"
  style="width: 200rpx"
></image>
```

标签属性

```
src - 图片资源地址
mode - 图片裁剪、缩放的模式
```

mode 部分合法值

{% asset_img mode.png 部分合法值 %}

最后再试一下这个例子

```html
<image
  src="https://jserclub.github.io/2019/08/13/trial-class/2.png"
  mode="widthFix"
  style="width: 200rpx"
></image>
<image
  src="https://jserclub.github.io/2019/08/13/trial-class/2.png"
  mode="widthFix"
  style="width: 200rpx"
></image>
```

**我们可以发现多个 image 标签写在一起的话，这些图片会在一行内显示。这也是一个重要特点，对于页面填充很重要！**

**思考**

如果相邻的两个图片我们希望他们不在一行内显示应该怎么办？

##### 第三步开始根据目标页面写代码

我们先来填充页面的基本结构，也就是说先把 wxml 的代码内容敲出来。

在开始之前我们来看一下页面的内容，上来就是 Jser 与头像这两张图片，引入图片的方式我们知道是使用 image 标签，但是 image 有一个重要的特点是什么呀？
所以我根据我自己的编程经验，建议大家把页面的每一块都用 view 标签包裹起来，这样子等我们使用 wxss 布局的时候会特别方便。

### 给页面添加样式

---

页面的内容可以添加进去了，但是看起来一定很丑对不对；那么怎么才能做成我们想要的样子呢？接下来就该是样式登场的时候了。

#### 回忆我们学习的两个标签 view image

**思考：这两个标签的特点分别是什么？这两个特点是什么决定的呢？我能不能让 view 的特点消失呢？**

事实上决定这两个标签的特点的是样式属性 — display；请看微信小程序开发者工具

```css
属性名: display
属性值: block (块级元素)  inline (行内元素) inline-block (行内块)
```

块级元素： 相邻标签会换行显示，可设置宽高
行内元素： 相邻标签会在一行显示，不可设置宽高
行内块元素： 相邻标签会在一行显示，可设置宽高

#### 那么我们如何给我们的标签添加样式呢？

还记得我们如何给图片设置大小吗？

```html
<image
  src="https://jserclub.github.io/2019/08/13/trial-class/2.png"
  mode="widthFix"
  style="width: 200rpx"
></image>
```

这个里面的style就是设置样式的关键字。

#### 那我们将要用到哪些样式属性呢？

```css
width - 设置盒子的宽度
height - 设置盒子的高度
font-size - 设置字体大小
font-weight - 指定了字体的粗细程度。一些字体只提供normal和bold两种值。
text-align - 规定盒子内的行内元素的对齐方式 left、right、center
margin - 外边距，暂时可以理解为相邻盒子的间距
```

