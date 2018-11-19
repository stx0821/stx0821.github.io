---
title: JavaScript 进行浮点运算的一个“bug”
tags:
  - JavaScript
id: 86
categories:
  - WEB技术
date: 2016-03-21 10:55:11
---

可能是平时用javascript不怎么做浮点运算的原因，这么明显的运算结果出错居然一直没发现过。

[![2016-03-21_102705](http://www.mddup.com/wp-content/uploads/2016/03/2016-03-21_102705.png)](http://www.mddup.com/wp-content/uploads/2016/03/2016-03-21_102705.png)

很难想像，这种小学生都会的小数运算减法，计算机居然会出错。

究其原因，计算机在做整数运算时是不会出错的，但一碰到小数有时候就懵了（可能是因为十进制小数不能很好转换成二进制），具体资料可以参见：[IEEE754标准](http://baike.baidu.com/view/1698149.htm?fromtitle=IEEE754%E6%A0%87%E5%87%86&amp;fromid=10427270&amp;type=syn "IEEE754%E6%A0%87%E5%87%86&amp;fromid=10427270&amp;type=syn")。

所以以后尽量避免使用浮点进行运算，减少不必要的麻烦。