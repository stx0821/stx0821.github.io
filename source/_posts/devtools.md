---
title: devtools note
date: 2020-09-19 12:57:39
tags:
---
# chrome devtools 

## copy(obj)

copy(anything) 是一个很有用的工具函数方便你将任何东西拷贝到系统的粘贴板暂存。

给copy函数传入一个没有格式的JSON，会返回格式化的结果：

## 阻塞请求
在 Network 标签页下，选中一个请求，右击该请求，选择 Block request domain 或 Block request URL，可以分别阻塞该请求所在 domain 下的所有请求 和 该请求。

## 手动给元素添加一个点击事件监听
在 debug 的时候，有时候需要在元素的点击事件监听函数中，将该点击事件对象打印出来。有个更方便的方式，是可以直接在 Elements 标签页为页面元素添加事件监听事件。

操作：

在 Elements 标签页中选中一个页面元素（选中之后，默认可以通过 $0 变量获取到该元素 ）
在 Console 标签页中，调用函数 monitorEvents，输入两个参数，第一个是当前元素（$0），第二个是事件名（click）
按 Enter后，当被选中的元素触发了点击事件之后，Console 标签页会将该点击事件对象打印出来

## 缓存上一步操作的结果
在 Chrome DevTools 上运行 JavaScript 表达式的时候，可以使用 $_ 来获取到上一步操作的返回值。
$x 可以用xPath的语法来获取页面上的元素；

## Overrides 重写
在 Chrome DevTools上调试 css 或 JavaScript时，修改的属性值在重新刷新页面时，所有的修改都会被重置。如果你想把修改的值保存下来，刷新页面的时候不会被重置，那就看看下面这个特性（Overrides）吧。Overrides默认是关闭的，需要手动开启，开启的步骤如下。

开启的操作：

打开 Chrome DevTools 的 Sources 标签页
选择 Overrides 子标签
选择 + Select folder for overrides，来为 Overrides 设置一个保存重写属性的目录


## 跳转到特定的行数
当你打开一个在源标签里的文件之后，DevTools能够允许你轻松地跳转到代码里的任意一行，Windows 和 Linux用户只需要按下Ctrl + G (在Mac上使用 Cmd + L )，然后输入你想查阅的行数即可。

## 选择下一个匹配项
当你在Sources 标签下编辑文件时，如果你按下Ctrl + D (Cmd + D)，下一个匹配项也会被选中，这能够帮助你同时编辑他们。


## 改变颜色格式
在颜色预览中使用Shift + Click ，可以在rgba, hsl 和 hexadecimal 这三种格式中改变。

## ctrl+shift+e 在控制台运行当前选中的代码片段

## netWork网络请求过滤器
larger-than:100将 查找大于100个字节的资源并进行筛选。
您可以通过在查询前面加上“-”来否定查询。例如：-larger-than:50K找到以下资源不大于50K。
status-code: 200若要查找具有状态代码响应的资源，请执行以下操作200
mime-type 查找请求资源类型

## 通过h来隐藏
可以按下h来隐藏在元素面板中被你选中的元素。再次按下h使它出现。某些时候这是很有用的，例如你想截图，但是又不想里面包含一些敏感信息。


