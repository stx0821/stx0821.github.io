---
title: ES6
date: 2020-09-19 12:32:39
tags:
  - JavaScript
categories:
  - 笔记
---

# Symbol
有一个Object.getOwnPropertySymbols()方法，可以获取指定对象的所有 Symbol 属性名。该方法返回一个数组，成员是当前对象的所有用作属性名的 Symbol 值。
另一个新的 API，Reflect.ownKeys()方法可以返回所有类型的键名，包括常规键名和 Symbol 键名。
