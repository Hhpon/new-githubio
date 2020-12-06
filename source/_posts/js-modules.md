---
title: js-modules
date: 2020-08-02 20:00:37
tags:
description: module.exports、exports、export、export default之间的区别到底是什么呢?
---

我们在开发 express、koa、egg、vue、react、angular 总是能看到这些内容，但是真的到自己使用的时候又不知道该怎么用。今天我们就来学习一下这些模块导出的用法。

### CommonJs 模块

---

Node 应用是由模块组成的，采用 CommonJs 模块规范。

根据这个规范，每个文件就是一个模块，有自己的作用域。在一个文件里面定义的变量、函数、类，都是私有的，对其他文件不可见。

CommonJS 规范规定，每个模块内部，module 变量代表当前模块。这个变量是一个对象，它的 exports 属性（即 module.exports）是对外的接口。加载某个模块，其实是加载该模块的 module.exports 属性。

#### 使用方法

---

**使用module.exports导出模块**

```js
// demo.js

const x = 1

const add = function (val) {
  return val + x
}

module.exports.x = x
module.exports.add = add
```

**使用require导入模块**

```js
//demo1.js
const demo = require("./demo.js")
console.log(demo.x) // 1
console.log(demo.add(1)) //2
```

**exports 与 module.exports**

为了方便，Node为每个模块提供一个exports变量，指向module.exports。这等同在每个模块头部，有一行这样的命令。

```js
var exports = module.exports;
```

于是我们可以直接在 exports 对象上添加方法，表示对外输出的接口，如同在module.exports上添加一样。注意，不能直接将exports变量指向一个值，因为这样等于切断了exports与module.exports的联系。

**使用exports导出模块**

```js
// demo.js
const x = 1

const add = function (val) {
  return val + x
}

exports.x = x
exports.add = add
```

**使用require导入模块**

```js
//demo1.js
const { x, add } = require("./demo.js")
console.log(x) // 1
console.log(add(1)) //6
```

### ES6-模块
---

ES6， 全称 ECMAScript 6.0 ，是 JavaScript 的下一个版本标准，2015.06 发版。

ES6 主要是为了解决 ES5 的先天不足，比如 JavaScript 里并没有类的概念，但是目前浏览器的 JavaScript 是 ES5 版本，大多数高版本的浏览器也支持 ES6，不过只实现了 ES6 的部分特性和功能。

[ES6 入门教程]](https://es6.ruanyifeng.com/)

不同于CommonJS，ES6使用 export 和 import 来导出、导入模块。

#### 使用方法

---

**使用export导出**

```js
//demo2.js
export const str = 'hello world'

export function fuunc(a){
    return a+1
}
```

**使用import导入**

```js
//demo3.js
import { str, func } from './demo1'
```


**使用export default导出**

```js
//demo2.js
export default const str = 'hello world'
```

```js
const str = 'hello world'
export default str
```

**使用import导入**

```js
//demo3.js
import str from './demo1'
```