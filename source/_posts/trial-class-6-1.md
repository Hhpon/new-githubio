---
title: Jser 第九期训练营
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

正如上面所说，前端开发的生态环境已经相当完善，除了手机端的有赞小程序 UI 组件；还有[手机端有赞网页 UI 组件](https://youzan.github.io/vant/#/zh-CN/)、[PC 端饿了么网页 UI 组件](https://element.eleme.cn/#/zh-CN/component/installation)、[图标库](https://www.iconfont.cn/)

**初学者容易犯的错误：试图去了解组件的结构。**

其实组件可以理解成生活中的一个工具，比如鼠标、电脑、手机，我们不需要去了解其中的具体原理，我们只需要知道怎么使用就可以；组件也是一样，其实不光组件，我们在计算机中的很多东西都和组件有着异曲同工的特点。

所以前端开发已经很“接地气了”，把前端的三大基础学好就可以使用这些非常方便的 UI 组件；就可以简单高效的开发出自己喜欢的页面！

而我们今天就简单的体验一下这种引入“写好的”代码的模式；

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
<h1></h1>
<h2></h2>
<h3></h3>
<h4></h4>
<h5></h5>
<h6></h6>
<div></div>
<img />
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

**总结：路径就是地址，也就是引入哪个文件 => 等同于播放哪个视频文件**

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
    <!-- 此处的class相当于给标签起个名字 -->
    <div class="box"></div>
  </body>
</html>
```

**第一个项目总结：第一个项目应用的是 html 的基本结构以及 CSS，在本项目中主要是希望能为大家了解 html 与 css 的功能，以及为第二个项目以及明天的爬虫课程做铺垫。有问题可以随时提问呀！**

### 第二个项目：满屏小心心

---

{% asset_img 满屏爱心.gif 小心心 %}

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

#### ② 在页面中建立爱心的基本结构

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="./index.css" />
  </head>
  <body>
    <!-- 此处的id也相当于给标签起个名字 -->
    <div id="heart"></div>
  </body>
</html>
```

**第二个项目总结：第二个项目中使用了 html、css 和 js，在本项目中我们使用 html 搭建了页面的基本结构，使用 css 装饰了页面样式，使用 js 实现了"爆炸"的交互效果。那么我们使用前端除了网页基本的展示数据还有哪些进阶的功能呢?**

展示类：数据可视化
数据获取类：网易云重度用户数据分析
趣味类：有趣的简历

{% asset_img 建模A题.png 搜集数据 %}

这是正在进行东三省建模比赛 A 题，阅读题目可以发现，要做这道题的前提就是搜集数据；历年的数学建模题目中都会有类似的搜集数据的题目，那么我们要如何搜集这成百上千的数据呢？

**答：爬虫**

数据最后存在哪里呢？

**答：表格或者数据库**

此次课程接下来要讲的就是如何使用 python 操作 excel 表格

### 第三个项目：Excel 表格的自动化处理

---

在 python 中基本全都是"组件"的工具，比如我们要用到的 openpyxl、selenium,稍微有点不同的是 python 中的工具更全面，类似一个工具箱，我们可以从中获取多个数据，比如接下来的这个例子。

{% asset_img 原始成绩.png 400 原始成绩.png %}
{% asset_img 成绩.png 400 成绩.png %}

问题背景：现在一个学校的某个班级的成绩表格如上图原始成绩.png，任务是转换成成绩.png;

**分析：其实表格少的话其实很容易就能转换了，试想如果要整理全校的怎么办？初略统计，农大每次智育成绩表格大概有 1600+个表格。**

**代码逻辑分析：使用 python 先打开 excel 文件并读取表格内容，存储到内存后清洗数据并新建一个表格把数据存储进去；**

{% asset_img openpyxl.png 流程.png %}

上手准备：python 环境、VSCODE 编辑器、openpyxl(python 操控 excel 的包)

知识点：python 的重要数据结构 --- 数组

```python
arr = ['数学','语文','英语','物理','生物','化学','历史']
# 编程中最基本概念遍历：对数组的每一项进行操作
# 数组有个很重要的方法：append
subject.append('地理')
print(subject)
for subject in arr:
  print(subject)
```

```python
# 二维数组遍历
arr1 = [['数学','语文','英语','物理','生物','化学','历史'],['数学','语文','英语','物理','生物','化学','历史'],['数学','语文','英语','物理','生物','化学','历史'],['数学','语文','英语','物理','生物','化学','历史']]
for arr in arr1:
  for subject in arr:
    print(subject)
```

```python
# openpyxl 包的基本介绍
# load_workbook() 这是一个加载excel表格的函数，括号中需要输入需要解析的文件路径，该函数会返回一个表格的实例
oldworkbook = load_workbook('作业-原始成绩.xlsx')
# sheet 的名字
sheetnames = oldworkbook.sheetnames
print(sheetnames)
# sheet名字对应的表格内容
sheet = oldworkbook[sheetnames[0]]
print(sheet)
# 具体的单元格数据
cell = sheet['A2:G24']
print(sheet['A2'].value)n

# 清洗数据第一步：提取有用数据
# 备注：这个地方很绕，初学者很难绕开，小白不要钻牛角尖，我们按照步骤一步步走
all = []
for x in cell:
    row = []
    for y in x:
        row.append(y.value)
    all.append(row[:1]+row[4:])
print(all)

# Workbook() 这是一个新建excel表格的函数，括号中通常什么都不写；ps：注意字母大小写
newworkbook = Workbook()
newsheet = newworkbook.active
newsheet.title = '清洗后的数据'
newsheet.append(["学号", "姓名", "检测", "讨论", "成绩"])
# 我们每一次在newsheet中append都会增加一行数据，试想，如果我们添加30行，那么一个班级的人数是不是就够了
# newsheet.append(['A07140061', '韩慧鹏', '100', '0', '90'])

for n in all:
    print(n)
    studentID = n[0][5:13]
    studentName = n[0][13:]
    test = n[1]
    if n[2] == '-':
        discuss = 0
    else:
        discuss = n[2]
    score = n[3]
    newsheet.append([studentID, studentName, test, discuss, score])

newworkbook.save('new作业.xlsx')
```

### 第四个项目：爬虫 -- “真”小白就能上手的爬虫

---

爬虫的本质其实就是模仿自己在网页中的具体操作进行数据请求的一个过程；

{% asset_img 传统爬虫方式.png 传统爬虫方式.png %}

传统爬虫的难点：需要分析网页请求，需要在控制台中分析多条请求并找出哪些条是需要模拟的
selenium 爬虫的特点：操作完全是运行在浏览器中，就好像我们自己在操控电脑一样；

{% asset_img selenium.png selenium.png %}

正常在网页上面浏览步骤大致如下，此步骤也是我们一会使用 selenium 的操作；此前我们需要先来了解一下 selenium 这个 python 拓展包

```python
# selenium 包的基本介绍

# from selenium import webdriver
# 打开Chrome浏览器
driver = webdriver.Chrome()
# 打开网址'https://weixin.sogou.com/'
driver.get('https://weixin.sogou.com/')

# from selenium.webdriver.support.wait import WebDriverWait
# WebDriverWait(driver, timeout, poll_frequency=0.5, ignored_exceptions=None)
# driver：WebDriver 的驱动程序(Ie, Firefox, Chrome 或远程)
# timeout：最长超时时间，默认以秒为单位
# poll_frequency：休眠时间的间隔（步长）时间，默认为 0.5 秒
# ignored_exceptions：超时后的异常信息，默认情况下抛 NoSuchElementException 异常

# WebDriverWai()一般由unit()或until_not()方法配合使用
# until(method, message=’’) 调用该方法提供的驱动程序作为一个参数，直到返回值不为 False。
# until_not(method, message=’’) 调用该方法提供的驱动程序作为一个参数，直到返回值为 False。

# 等待页面加载出搜索框
wait = WebDriverWait(driver, 10)
input = wait.until(EC.presence_of_element_located((By.NAME, 'query')))
# 搜索框加载出来以后我们键入想要搜索的公众号文章
input.send_keys('数学建模之路')
# 点击“搜文章”按钮
driver.find_element_by_xpath("//input[@class='swz']").click()

# from selenium.webdriver.support import expected_conditions as EC
# expected_conditions是Selenium的一个模块，selenium.webdriver.support.expected_conditions，可以对网页上元素是否存在
```
