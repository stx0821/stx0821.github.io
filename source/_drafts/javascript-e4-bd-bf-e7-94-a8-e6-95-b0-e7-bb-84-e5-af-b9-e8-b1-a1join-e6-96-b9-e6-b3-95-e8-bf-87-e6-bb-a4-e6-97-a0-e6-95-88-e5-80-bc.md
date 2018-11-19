---
title: javascript使用数组对象join()方法过滤无效值
tags:
  - JavaScript
id: 89
categories:
  - WEB技术
---

在处理数据时，过滤和筛选出有效的数据是经常要做的事，使用的方法无非是对数据进行循环遍历，但某些情况下，利用语言内置的方法也可以达到相同的效果。
<pre>var arr = [100,true,undefined,'str',null];
arr.join(' '); //输出"100 true  str " 过滤掉了无效的undefined和null
</pre>
join方法用于把数组中的所有元素放入一个字符串，元素是通过指定的分隔符进行分隔的。该方法内部已经对无效的数据进行了处理，而不是简单的把所有数据转换成字符串输出。

<div class="alert alert-info">
如果你够前卫，可以使用ECMAscript5里最新的filter方法来过滤，如下：
</div>
<pre>
[100,true,undefined,'str',null].filter(function(v,i,t){ return v}) //返回值为[100, true, "str"]
</pre>