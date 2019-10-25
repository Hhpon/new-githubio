---
title: Node.js 项目入门
date: 2019-10-25 18:42:39
tags:
---

### 创建第一个 Node.js 的项目

---

新建一个项目的文件夹，起名为 “blogExpress”，接下来的一切操作需要全都在这一个文件夹里完成。不要弄混。

使用 Vscode 打开项目文件夹(即 blogExpress),在“查看”工具栏下点击“终端”按钮，Vscode 下方会弹起一个黑框框，此为“命令行”；

在命令行内输入如下命令初始化项目,输入之后命令行内会出现一些需要配置的内容，新手可无视，对于每一项直接回车就好。

```bash
npm init
```

初始化项目之后，需要为我们的第一个项目引入 Express。

```bash
npm install express --save
```

在项目文件夹下新建一个文件“app.js”，把下面的内容写到“app.js”里面

```js
const express = require("express");
const app = express();

app.get("/", function(req, res) {
  res.send("Hello World!");
});

app.listen(3000, function() {
  console.log("Example app listening on port 3000!");
});
```

在命令行输入命令，运行服务器,如果在命令行看到了“Example app listening on port 3000!”这一句话即证明服务器开启成功！否则请根据报错信息排查错误。

```bash
node app.js
```

开启成功以后可以打开浏览器在地址栏输入：localhost:3000
回车以后可以看到“Hello World”字样。

到此为止，项目最基本的已经搭建完毕，接下来我们就可以根据自己的需求来实现我们的服务器了。

npm 5.0+ 版本在默认情况下会将安装的模块添加到 package.json 文件中的 dependencies 列表中。对于较老的 npm 版本，你就必须指定 –save 参数。然后，照旧执行 npm install 命令即可自动安装依赖列表中所列出的所有模块。

### Blog 服务端代码

---

中间件：就好比我们浏览器的插件，插件可以弥补浏览器某些方面的不足，而中间件相对于 Express 而言与之相同。

body-parser 是一个 HTTP 请求体解析中间件，使用这个模块可以解析 JSON、Raw、文本、URL-encoded 格式的请求体，Express 框架中就是使用这个模块做为请求体解析中间件。

npm i body-parser –save

[body-parser 教程](https://www.jianshu.com/p/ea0122ad1ac0)

```js
const express = require("express"); //引入 express 框架
const bodyParser = require("body-parser"); // 引入 body-parser 中间件
const Article = require("./article-db"); // 引入数据库

const app = express(); // 把 express 实例化

app.use(express.static("public")); // 使用静态文件
app.use(bodyParser.json()); // 使用中间件

app.post("/article", function(req, res) {
  // 新建的路由，以及此路由实现的功能

  Article.create(
    {
      articleTitle: req.body.title,
      articleAuthor: req.body.author,
      articleContent: req.body.content
    },
    (err, doc) => {
      if (err) {
        res.end("no");
      } else {
        res.end("ok");
      }
    }
  );
});

app.get("/getArticle", function(req, res) {
  // 新建的路由，以及此路由实现的功能
  Article.find((err, doc) => {
    console.log(doc);
    res.json(doc);
  });
});

app.listen(3000, function() {
  console.log("服务器正在监听 3000 端口");
});
```

### 引入数据库

---

[mongoose 教程](https://www.cnblogs.com/xiaohuochai/p/7215067.html?utm_source=itdadao&utm_medium=referral)

```js
const mongoose = require("mongoose");

mongoose.connect("mongodb://localhost:27017/article", {
  useNewUrlParser: true
}); //连接数据库

const articleSchema = new mongoose.Schema({
  //schema
  articleTitle: String,
  articleAuthor: String,
  articleContent: String
});

module.exports = mongoose.model("article", articleSchema); // model
```
