---
title: HTML5 pattern属性是否需要^和$强制开头与结尾
tags:
  - HTML5
id: 88
categories:
  - WEB技术
date: 2016-05-03 11:07:08
---

近日在写一个手机号文本输入框时，用pattern属性验证手机号是否正确发现一个细节，pattern属性里的正则表达式和编程语言里的相比，是不需要使用^和$强制开头与结尾。即使你不写^和$，浏览器在解释时，也会隐式的在开头和结尾加上，就像：`^(?:your pattern)$`这样。
所以下面两行代码是完全等价的。
<!--more-->
<pre>&lt;input type="tel" name="tel" pattern="1[34578]\d{9}" title="11位手机号码" required /&gt;
&lt;input type="tel" name="tel" pattern="^1[34578]\d{9}$" title="11位手机号码" required /&gt;
</pre>
值得一提的是`type="tel"`不像`type="email"`和`type="number"`具有验证功能，这是W3C规定的，因为考虑到全世界类型繁多的电话号难以统一。所以在电脑上`type="tel"`的效果和普通文本框没什么区别，但其实是支持`type="tel"`的，如果在手机上会调出数字键盘，方便输入。
参考资料：[https://www.w3.org/TR/2014/REC-html5-20141028/forms.html#attr-input-pattern](https://www.w3.org/TR/2014/REC-html5-20141028/forms.html#attr-input-pattern)