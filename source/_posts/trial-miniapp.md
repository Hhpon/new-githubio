---
title: Jser训练营
date: 2019-10-16 19:47:34
tags:
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

我们先来填充页面的基本结构，也就是说先把wxml的代码内容敲出来。

在开始之前我们来看一下页面的内容，上来就是Jser与头像这两张图片，引入图片的方式我们知道是使用image标签，但是image有一个重要的特点是什么呀？
所以我根据我自己的编程经验，建议大家把页面的每一块都用view标签包裹起来，这样子等我们使用wxss布局的时候会特别方便。
