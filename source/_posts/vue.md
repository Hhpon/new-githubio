---
title: Vue 项目入门
date: 2019-11-08 15:04:04
tags:
---

### Vue.js 是什么

---

Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式框架。

### 起步

---

如果你还没有使用过 Vue,建议你使用 CDN 引入,当你熟悉 npm 这个构建工具以后可以自己上手试试 Vue-cli。

```js
<!-- 开发环境版本，包含了有帮助的命令行警告 -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
```

[vue.js cdn](https://www.bootcdn.cn/vue/)

### 声明式渲染

---

我们可以把页面上的内容用 Vue.js 绑定，即当我们想在某一时刻想改变页面内容的时候我们可能会用到。

```js
<div id="app">{{ message }}</div>
```

```js
const app = new Vue({
  el: "#app",
  data: {
    message: "Hello Vue!"
  }
});
```

除此之外，某些时候我们希望改变的是标签的某些属性，比如说我们希望在点击某张图片的时候改变这张图片，那么我们就需要改变图片的地址。

```js
<div id="app">
  <img v-bind:src="imgSrc" v-on:click="handle()" />
</div>
```

```js
const app = new Vue({
  el: "#app",
  data: {
    imgSrc: "1.jpg"
  },
  methods: {
    handle: function() {
      this.imgSrc = "2.jpg";
    }
  }
});
```

### 条件与循环

---

或许有时候你想隐藏一个节点

```js
<div id="app-3">
  <p v-if="seen">现在你看到我了</p>
</div>
```

```js
const app3 = new Vue({
  el: "#app-3",
  data: {
    seen: true
  }
});
```

如果你把 data 里面的 seen 改成 false 那么这个节点就会消失，如果你能用一个方法改变 seen 的值，那么你就能让这个节点动态的显示了。

或许有的时候我们希望显示在页面上的是从服务器传过来的一个数组，使用 v-for 指令可以渲染一个数组。

```js
<div id="app-4">
  <ol>
    <li v-for="todo in todos">
      {{ todo.text }}
    </li>
  </ol>
</div>
```

```js
const app4 = new Vue({
  el: "#app-4",
  data: {
    todos: [
      { text: "学习 JavaScript" },
      { text: "学习 Vue" },
      { text: "整个牛项目" }
    ]
  }
});
```

### 处理用户输入

---

为了让用户和你的应用进行交互，我们可以用 v-on 指令添加一个事件监听器，通过它调用在 Vue 实例中定义的方法：

```js
<div id="app-5">
  <p>{{ message }}</p>
  <button v-on:click="reverseMessage">逆转消息</button>
</div>
```

```js
const app5 = new Vue({
  el: "#app-5",
  data: {
    message: "Hello Vue.js!"
  },
  methods: {
    reverseMessage: function() {
      this.message = this.message
        .split("")
        .reverse()
        .join("");
    }
  }
});
```

Vue 还提供了 v-model 指令，它能轻松实现表单输入和应用状态之间的双向绑定。

```js
<div id="app-6">
  <p>{{ message }}</p>
  <input v-model="message" />
</div>
```

```js
var app6 = new Vue({
  el: "#app-6",
  data: {
    message: "Hello Vue!"
  }
});
```
