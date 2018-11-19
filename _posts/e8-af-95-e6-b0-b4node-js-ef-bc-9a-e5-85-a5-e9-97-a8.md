---
title: 试水Node.js：入门
tags:
  - JavaScript
  - Node.js
id: 63
categories:
  - WEB技术
date: 2015-12-22 16:25:48
---

Node（即Node.js）用一句来说就是运行在服务器端的JS，类似于PHP，JSP，.NET等后端语言。用它可以操作磁盘文件或搭建HTTP服务器等等，相较于前端JS，Node提供了`fs`、`http`等内置对象。

<!--more-->

## 1.安装

安装Node.js没什么好说的，一直点下一步直至完成即可，和安装一般的应用软件没什么区别，如下图所示。

[![1](http://www.mddup.com/wp-content/uploads/2015/12/1-300x235.png)](http://www.mddup.com/wp-content/uploads/2015/12/1.png)

下载地址：[http://nodejs.org/dist/v0.10.26/node-v0.10.26-x86.msi](http://nodejs.org/dist/v0.10.26/node-v0.10.26-x86.msi)

## 2.运行

打开CMD，键入`Node`进入命令交互模式，这里面可以写任何ECMAscript的语法规则，可以输入一条代码语句后立即执行并显示结果，例如：
<pre>`node
&gt; console.log('hello world!');
hello world!`
</pre>
[![1](http://www.mddup.com/wp-content/uploads/2015/12/1-300x220.gif)](http://www.mddup.com/wp-content/uploads/2015/12/1.gif)
点击图片查看gif

如果一条语句未结束，Node会自动判断，会以三个...表示可以继续输入。

[![2](http://www.mddup.com/wp-content/uploads/2015/12/2-300x251.gif)](http://www.mddup.com/wp-content/uploads/2015/12/2.gif)

很多时候这种在命令行直接写JS的方法并不常用，更多的是保存为一个JS文件，然后用node 命令运行它，在D盘新建一个hello.js文件，内容为`console.log('hello world!');`然后转到D盘，输入node hello.js。

## 3.第一个HTTP服务器

Node不同于传统的后端语言需要apache，IIS服务器，Node本身就自带了HTTP服务器模块，新建一个JS文件，输入以下代码，并用node命令执行它。打开浏览器输入地址：http://127.0.0.1:8899/
<pre>var http = require('http');  //使用内置的require函数加载http模块
http.createServer(function(req, res) {
	res.writeHead(200, {'Content-Type': 'text/html'});
	res.end('&lt;h1&gt;Hello World&lt;/h1&gt;');   //对于任何请求都返回hello world
}).listen(8899); //监听8899端口 
console.log("server is running at port  8899.");
</pre>
[![4](http://www.mddup.com/wp-content/uploads/2015/12/4-300x251.png)](http://www.mddup.com/wp-content/uploads/2015/12/4.png)

[![3](http://www.mddup.com/wp-content/uploads/2015/12/3-300x163.png)](http://www.mddup.com/wp-content/uploads/2015/12/3.png)

这个只是最基本的HTTP服务器，对于任何请求（包括404）都返回200 hello world，所以你没办法通过URL访问静态资源。

我们还注意到，运行HTTP服务器后，命令行并没有退出，如果你修改了server.js文件，网页也不会响应你的修改，需要你自行重启。

PS：如果觉得这样太麻烦的话，可以使用supervisor工具，安装命令为npm i supervisor -g，执行JS时，使用supervisor server.js即可。

[![5](http://www.mddup.com/wp-content/uploads/2015/12/5-300x286.png)](http://www.mddup.com/wp-content/uploads/2015/12/5.png)

就目前看来Node.js水还是挺深的，后面还会涉及到很多知识，这些都还只是冰山一角。

而且由于Node更新极快，网络上很多关于Node的文章或者书籍，可能你对着敲一遍，结果还是会出错，因为版本更新后的使用方法可能完全不同，唯一权威的就是英文官网。

&nbsp;

&nbsp;