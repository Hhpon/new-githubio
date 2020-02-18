---
title: FlexBox
date: 2019-07-18 19:11:59
tags:
---

传统的布局方案: 盒模型 + 定位(position) + 浮动(Float)，不适合现如今的响应式布局；

{% asset_img brower.jpg 支持的浏览器汇总 %}

**响应式布局:响应式布局是Ethan Marcotte在2010年5月份提出的一个概念，简而言之，就是一个网站能够兼容多个终端——而不是为每个终端做一个特定的版本。 这个概念是为解决移动互联网浏览而诞生的。**

### 知识点与实践

---

**知识点**

- 什么是容器、项目
- 容器内的div盒子排列方式会发生变化吗
- 会按照什么方向排列
- 如何改变div盒子排列方向
- 如何设置在排列方向上的对齐方式
- 如何盒子的水平与垂直居中
- 一行排满项目之后盒子会换行显示吗，换行显示的命令是什么
- 容器属性有哪些、项目属性有哪些
- 当盒子排列的时候，存在剩余空间的情况下，盒子会变大会变小
- 如果空间不足盒子会变大会变小
- 如何阻止盒子变大或者变小
- 如何设置项目的顺序

### Flex 布局是什么？

***

Flex 是 Flexible Box 的缩写，意为”弹性布局”，用来为盒状模型提供最大的灵活性。

设置 Flex 布局的方法:

```css
display:flex;
```

### 基本概念
***

采用 Flex 布局的元素，称为 Flex 容器（flex container），简称”容器”。它的所有子元素自动成为容器成员，称为 Flex 项目（flex item），简称”项目”。

**初学者最容易忽略‘容器’与‘项目’的概念**

{% asset_img flex1.png Flex 布局示意图 %}

容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）。主轴的开始位置（与边框的交叉点）叫做main start，结束位置叫做main end；交叉轴的开始位置叫做cross start，结束位置叫做cross end。

项目默认沿主轴排列。单个项目占据的主轴空间叫做main size，占据的交叉轴空间叫做cross size。

### 容器的属性
***

```
flex-direction
flex-wrap
flex-flow
justify-content
align-items
align-content
```

#### justify-content属性

justify-content属性定义了项目在主轴上的对齐方式。(主轴一定要有大小 – 宽度或者高度);

```css
.box {
  justify-content: flex-start | flex-end | center | space-between | space-around;
}
```
```
flex-start（默认值）：左对齐
flex-end：右对齐
center： 居中
space-between：两端对齐，项目之间的间隔都相等。
space-around：每个项目两侧的间隔相等。所以，项目之间的间隔比项目与边框的间隔大一倍。
```

{% asset_img justify-content.png justify-content %}


#### align-items属性

align-items属性定义项目在交叉轴上如何对齐。

```css
.box {
  align-items: flex-start | flex-end | center | baseline | stretch;
}
```
```
flex-start：交叉轴的起点对齐。
flex-end：交叉轴的终点对齐。
center：交叉轴的中点对齐。
baseline: 项目的第一行文字的基线对齐。
stretch（默认值）：如果项目未设置高度或设为auto，将占满整个容器的高度。
```

{% asset_img align-item.png align-item %}

#### flex-direction属性

flex-direction属性决定主轴的方向(即项目的排列方向)。

```css
.box {
  flex-direction: row | row-reverse | column | column-reverse;
}
```
```
row（默认值）：主轴为水平方向，起点在左端。
row-reverse：主轴为水平方向，起点在右端。
column：主轴为垂直方向，起点在上沿。
column-reverse：主轴为垂直方向，起点在下沿。
```

{% asset_img flex-direction.png direction %}

#### flex-wrap属性

默认情况下，项目都排列在一条轴线上。flex-wrap属性定义，如果一条轴线排不下，该如何换行。(默认不换行的时候会自动伸缩，即设置的大小会伸缩);

```css
.box{
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```

三个值分别为:

（1）nowrap（默认）：不换行。

{% asset_img wrap1.png %}

（2）wrap：换行，第一行在上方。

{% asset_img wrap2.jpg %}

（3）wrap-reverse：换行，第一行在下方。

{% asset_img wrap3.jpg %}

#### flex-flow

flex-flow属性是flex-direction属性和flex-wrap属性的简写形式，默认值为row nowrap。

```css
.box {
  flex-flow: <flex-direction> || <flex-wrap>;
}
```

#### align-content 属性

align-content属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。
align-content定义的是行与行之间，交叉轴方向的多余空间要如何分布。

```css
.box {
  align-content: flex-start | flex-end | center | space-between | space-around | stretch;
}
```
```
flex-start：与交叉轴的起点对齐。
flex-end：与交叉轴的终点对齐。
center：与交叉轴的中点对齐。
space-between：与交叉轴两端对齐，轴线之间的间隔平均分布。
space-around：每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍。
stretch（默认值）：轴线占满整个交叉轴。
```

{% asset_img align-content.png align-content %}

### 项目属性
***

```
order
flex-grow
flex-shrink
flex-basis
flex
align-self
```

#### flex-grow属性

flex-grow属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。

```css
.item {
  flex-grow: <number>; /* default 0 */
}
```

{% asset_img flex-grow.png flex-grow %}

如果所有项目的flex-grow属性都为1，则它们将等分剩余空间（如果有的话）。如果一个项目的flex-grow属性为2，其他项目都为1，则前者占据的剩余空间将比其他项多一倍。

#### flex-shrink属性

flex-shrink属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。

```css
.item {
  flex-shrink: <number>; /* default 1 */
}
```

{% asset_img flex-shrink.jpg flex-shrink %}

如果所有项目的flex-shrink属性都为1，当空间不足时，都将等比例缩小。如果一个项目的flex-shrink属性为0，其他项目都为1，则空间不足时，前者不缩小。

负值对该属性无效。

#### flex-basis属性

```css
.item {
  flex-basis: <length> | auto; /* default auto */
}
```

flex-basis 设置的是主轴方向上项目占据的空间，并且优先级高于height与width。

#### flex属性

flex属性是flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto。后两个属性可选。

```css
.item {
  flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
}
```

该属性有两个快捷值：auto (1 1 auto) 和 none (0 0 auto)。

建议优先使用这个属性，而不是单独写三个分离的属性，因为浏览器会推算相关值。

#### align-self属性

align-self属性允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。默认值为auto，表示继承父元素的align-items属性，如果没有父元素，则等同于stretch。

```css
.item {
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
```

{% asset_img align-self.png align-self %}

该属性可能取6个值，除了auto，其他都与align-items属性完全一致。

#### order属性

order属性定义项目的排列顺序。数值越小，排列越靠前，默认为0。

```css
.item {
  order: <integer>;
}
```

{% asset_img order.png order %}