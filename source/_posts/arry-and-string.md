---
title: 数组和字符串的相关方法
date: 2020-07-14 14:00:36
tags:
---

### 声明:var

---

```
var arr=[1,2,3]//声明一个数组
```
声明了一个叫arr的数组，数组里依次是1、2、3三个数字
```
var str="123"//声明一个字符串
```
声明了一个叫str的字符串，字符串里有123，注意，它已经不是数字了

---

### 获取长度:length

---

```
XXX.length//获取名为XXX的字符串或数组的长度
```
比如有一个叫arr数组里依次是1、2、3三个数字，调用`arr.length`将会得到3
比如有一个叫str的字符串，字符串里是abcd，调用`str.length`将会得到4
当然这行代码直接执行没有意义，你需要声明一个变量把获取到的长度存起来
```
var a=XXX.length
```
或者直接把长度显示在控制台中
```
console.log(XXX.length)
```

---
### 截取:slice
---

```
arr.slice(a,b)//返回一个新的数组，包含下标从a到b（不包括该元素）的arr中的数字
```
可使用负值从数组的尾部选取数字，如果b未被规定，那么 slice()方法会选取从a到数组结尾的所有数字。
比如arr数组里原先依次是1、2、3、4、5五个数字，调用`arr.slice(0,3)`将会得到1、2、3
当然这行代码直接执行没有意义，你需要声明一个数组把操作之后的数组存起来
```
var arr1=arr.slice(0,3)
```
或者直接把截取的数组显示在控制台中
```
console.log(arr.slice(0,3))
```
或者直接修改原来的数组
```
arr=arr.slice(0,3)
```
```
str.slice(a,b)//返回一个新的字符串，包含下标从a到b（不包括该元素）的str中的字符
```
比如str字符串里原先有12345,调用`str.slice(0,3)`将会得到123
当然这行代码直接执行也没有意义，你可能会遇到的情况和对应的操作方法同*截取数组*

---
### 合并:concat
---

```
arr1.concat(arr2)//返回一个新的数组，把arr2接在arr1后面
```
比如arr1数组里原先依次是1、2、3三个数字，arr2数组里原先依次是4、5、6三个数字，调用`arr1.concat(arr2)`将会得到1、2、3、4、5、6
当然这行代码直接执行也没有意义，你可能会遇到的情况和对应的操作方法同*截取数组*
字符串合并非常简单，直接用`+`就行了
```
str1+str2//把str2接在str1后面
```
比如str1字符串里原先有123，比如str2字符串里原先有456，调用`str1+str2`将会得到123456
当然这行代码直接执行没有意义，你需要声明一个字符串把操作之后的字符串存起来
```
var a=str1+str2
```
或者直接把合并后的字符串显示在控制台中
```
console.log(str1+str2)
```
或者直接修改原来的字符串
```
str1=str1+str2
```

---
### 查找
---

#### 查找首次出现位置:indexOf
```
XXX.indexOf(a,b)//查找名为XXX的字符串或数组从下标b开始首次出现a的下标
```
其中，b可以省略不写，当b省略不写时默认从头开始查找，当找不到时返回`-1`
比如arr数组里原先依次是1、2、3、4、1五个数字,调用`arr.indexOf(1)`将会得到0，调用`arr.indexOf(2)`将会得到1，调用`arr.indexOf(1,2)`将会得到4，调用`arr.indexOf(2，2)`将会得到-1
比如str字符串里原先有Hello,world!，调用`str.indexOf("Hello")`将会得到0，调用`str.indexOf("world")`将会得到6，调用`str.indexOf("Hello",2)`将会得到-1
当然这行代码直接执行没有意义，你可以把得出的结论显示在控制台中
```
console.log(arr.indexOf(1))
```
也可以用于接下来说的添加、替换和删除
#### 判断在不在数组里:in
```
a in XXX//判断a是否在名为XXX的数组里
```
比如arr数组里原先依次是1、2、3、4、5五个数字，调用`1 in arr`将会得到true，调用`0 in arr`将会得到false
当然这行代码直接执行没有意义，你可以把得出的结论显示在控制台中
```
console.log(1 in arr)
```
也可以用在判断语句和循环语句中
```
if(1 in arr)
	//do something
while(1 in arr)
	//do something
```
#### 判断在不在字符串里:includes
```
XXX.includes(a)//判断a是否在名为XXX的字符串里
```
比如str字符串里原先有123，str1字符串里原先有12，str2字符串里原先有13，调用`str.includes('1')`或`str.includes(str1)`都将会得到true，调用`str.includes('0')`或`str.includes(str2)`都将会得到false
注意，此方法区分大小写，比如str字符串里原先有abc，调用`str.includes('Abc')`将会得到false
当然这行代码直接执行也没有意义，你可能会遇到的情况和对应的操作方法同*判断在不在数组里*

---
### 添加
---

#### 在末尾添加:push
```
XXX.push(a)//在名为XXX的数组末尾添加a这个数字
```
比如arr数组里原先依次是1、2、3三个数字，执行`arr.push(4)`这个代码之后数组里就依次是1、2、3、4四个数字了
在字符串末尾添加字符串同*合并字符串*
```
XXX+"abc"//在名为XXX的字符串末尾添加abc这个字符串
```
比如str字符串里原先有123，调用`str+"abc"`将会得到123abc
当然这行代码直接执行也没有意义，你可能会遇到的情况和对应的操作方法同*合并字符串*
#### 在最前面添加:unshift
```
XXX.unshift(a)//在名为XXX的数组末尾添加a这个数字
```
比如arr数组里原先依次是1、2、3三个数字，执行`arr.push(4)`这个代码之后数组里就依次是4、1、2、3四个数字了
```
在字符串最前面添加字符串同*合并字符串*
"abc"+XXX//在名为XXX的字符串前面添加abc这个字符串
```
比如str字符串里原先有123，调用`"abc"+str`将会得到abc123
当然这行代码直接执行也没有意义，你可能会遇到的情况和对应的操作方法同*合并字符串*
#### 在中间添加:splice
```
XXX.splice(a,0,b)//在名为XXX的数组的第a项**之前**添加b这个数字
```
比如arr数组里原先依次是1、2两个数字，执行`arr.splice(1,0,3)`这个代码之后数组里就依次是1、3、2三个数字了
比如arr数组里原先依次是1、2、3、4、5五个数字，想要在2前面加上6这个数字，则需要执行`arr.splice(arr.indexOf(2),0,6)`
在字符串中间添加字符串是非常麻烦的，首先需要先把原先的字符串从要添加的位置分开成两部分，然后将前半部分不动，中间是要添加的字符串，最后是后半部分合并在一起
```
var newstr = str.slice(0,5)+"-local"+str.slice(5) 
```
比如str字符串里原先有Hello,world!
执行这段代码后newstr就变成了Hello-local,world!

---
### 替换:splice
---

```
XXX.splice(a,b,c)//将名为XXX的数组从第a+1项开始的连续b项替换成c
```
比如arr数组里原先依次是1、2、3、4、5五个数字，执行`arr.splice(2,1,6)`这个代码之后数组里就依次是1、2、6、4、5了，而执行`arr.splice(2,2,6)`这个代码之后数组里就依次是1、2、6、5了
字符串的替换就是截取不需要替换的部分，与需要替换的字符串拼接
比如arr数组里原先依次是1、2、3、4、5五个数字，想要把其中的2替换成6，则需要执行`arr.splice(arr.indexOf(2),1,6)`

---
### 删除
---

#### 从末尾删除:pop
```
XXX.pop()//删除名为XXX的数组末尾的数字
```
比如arr数组里原先依次是1、2、3、4四个数字，执行`arr.pop()`这个代码之后数组里就依次是1、2、3三个数字了
在字符串末尾删除字符串同*截取字符串*
#### 从最前面删除:shift
```
XXX.shift()//删除名为XXX的数组最前面的数字
```
比如arr数组里原先依次是1、2、3、4四个数字，执行`arr.shift()`这个代码之后数组里就依次是2、3、4三个数字了
在字符串末尾删除字符串同*截取字符串*
#### 从中间删除:splice
```
XXX.splice(a,b)//删除名为XXX的数组从第a+1项开始连续b项的数字
```
比如arr数组里原先依次是1、2、3、4、5五个数字，执行`arr.splice(2,1)`这个代码之后数组里就依次是1、2、4、5了，而执行`arr.splice(2,2)`这个代码之后数组里就依次是1、2、5了
字符串从中间删除就是截取不需要删除的部分拼接在一起
比如arr数组里原先依次是1、2、3、4、5五个数字，想要把其中的2删除，则需要执行`arr.splice(arr.indexOf(2),1)`

---
### 排序:sort
---

```
XXX.sort()//将名为XXX的数组中的数字从小到大排列
```
比如arr数组里原先依次是5、2、1、3、4五个数字，执行`arr.sort()`这个代码之后数组里就依次是1、2、3、4、5五个数字了
字符串没有排序功能

---
### 反转:reverse
---

```
XXX.reverse()//将名为XXX的数组反转
```
比如arr数组里原先依次是5、2、1、3、4五个数字，执行`arr.reverse()`这个代码之后数组里就依次是4、3、1、2、5五个数字了

---
### 字符串与数组的相互转换
---

#### 字符串转数组:split
```
XXX.split(a)//指定的分隔符字符串a将名为XXX的字符串分割成子字符串数组，以这个指定的分割字串a来决定每个拆分的位置
```
比如str字符串里原先有abc defxy ghi，调用`str.split(' ')`将会得到一个数组，这个数组里依次是abc，defxy，ghi三个字符串，调用`str.split（'')`将会得到一个长度为13的数组，里面依次是str字符串中的每个字符，调用`str.split('xy')`将会得到一个数组，这个数组里依次是abc def，ghi两个字符串，若指定的分隔字符在字符串里没有出现，比如调用`str.split('z')`或`str.split()`都将会得到一个长度为1的数组，里面是abc defxy ghi这个字符串
直接执行这些代码没有意义，你需要声明一个数组把得到的的数组存起来
```
var newstr=str.split(' ')
```
或者把得到的数组显示在控制台中
```
console.log(str.split(' '))
console.log(str.split(' ')[0])
```
也可以用在判断语句和循环语句中
```
if(str.split(' ')[0] == abc)
	//do something
while(str.split(' ')[0] == abc)
	//do something
```
还可以对结果进行数组才有的操作比如`arr.push(str.split(' ')[0])`等
#### 数组转字符串:join
```
XXX.join(a)//返回一个字符串，该字符串是通过先把名为XXX的数组中的每个元素转换为字符串，然后在相邻两个元素之间插入字符串a，再把这些字符串连接起来而生成的
```
比如arr数组里原先依次是5、2、1、3、4五个数字，调用`arr.join('.')`将会得到字符串5.2.1.3.4，调用`arr.join('')`将会得到52134，注意，当调用`arr.join()`与`arr.join(',')`都将会得到5,2,1,3,4
直接执行这些代码没有意义，你可能会遇到的情况和对应的操作方法同*合并字符串*

---
### 字符串大小写转换
---

#### 转换成大写:toUpperCase
```
XXX.toUpperCase()//返回一个新字符串，将名为XXX的字符串中的所有字母转换成大写字母
```
比如str字符串里原先有AbcD，调用`str.toUpperCase()`将会得到ABCD，但str字符串里还是AbcD
所以这行代码直接执行没有意义，你可能会遇到的情况和对应的操作方法同*合并字符串*
#### 转换成小写:toLowerCase
```
XXX.toLowerCase()//返回一个新字符串，将名为XXX的字符串中的所有字母转换成小写字母
```
比如str字符串里原先有AbcD，调用`str.toLowerCase()`将会得到abcd，但str字符串里还是AbcD
所以这行代码直接执行也没有意义，你可能会遇到的情况和对应的操作方法同*合并字符串*

---
### 字符串去空格
---

#### 去除头尾空格:trim
```
XXX.trim()//返回一个新字符串，为去除名为XXX的字符串开始和结尾的空格
```
比如str字符串里原先有&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;a&nbsp;b&nbsp;&nbsp;c&nbsp;&nbsp;&nbsp;&nbsp;，调用`str.trim()`将会得到a&nbsp;b&nbsp;&nbsp;c，但str字符串里还是&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;a&nbsp;b&nbsp;&nbsp;c&nbsp;&nbsp;&nbsp;&nbsp;
所以这行代码直接执行没有意义，你可能会遇到的情况和对应的操作方法同*合并字符串*
#### 去除左侧空格:trimStart
```
XXX.trimStart()//返回一个新字符串，为去除名为XXX的字符串中左侧的空格
```
比如str字符串里原先有&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;a&nbsp;b&nbsp;&nbsp;c&nbsp;&nbsp;&nbsp;&nbsp;，调用`str.trimStart()`将会得到a&nbsp;b&nbsp;&nbsp;c&nbsp;&nbsp;&nbsp;&nbsp;，但str字符串里还是&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;a&nbsp;b&nbsp;&nbsp;c&nbsp;&nbsp;&nbsp;&nbsp;
所以这行代码直接执行也没有意义，你可能会遇到的情况和对应的操作方法同*合并字符串*
#### 去除右侧空格:trimEnd
```
XXX.trimEnd()//返回一个新字符串，为去除名为XXX的字符串中右侧的空格
```
比如str字符串里原先有&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;a&nbsp;b&nbsp;&nbsp;c&nbsp;&nbsp;&nbsp;&nbsp;，调用`str.trimEnd()`将会得到&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;a&nbsp;b&nbsp;&nbsp;c，但str字符串里还是&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;a&nbsp;b&nbsp;&nbsp;c&nbsp;&nbsp;&nbsp;&nbsp;
所以这行代码直接执行也没有意义，你可能会遇到的情况和对应的操作方法同*合并字符串*