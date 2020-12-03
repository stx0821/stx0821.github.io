---
title: React Note
date: 2020-09-19 12:32:39
tags:
  - React
categories:
  - 笔记
---


不允许直接结对this.state.xxx接口，要先深拷贝下来操作
方法也可以父子传递
单向数据流只允许在父组件改变数据
this.setState是异步方法

```jsx
const element = <img src={user.avatarUrl}></img>;
```