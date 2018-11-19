---
title: ECMAScript5 对象&数组字面量扩展
tags:
  - ECMAScript
  - JavaScript
id: 103
categories:
  - WEB技术
date: 2016-05-05 17:52:21
---

ECMAscript5 对象&amp;数组字面量扩展 Object/array literal extensions如下：

1.  Getter accessors 获取访问器
2.  Setter accessors 设置访问器
3.  Trailing commas in object literals 对象字面量最后一个属性后面允许出现逗号
4.  Trailing commas in array literals 数组字面量最后一个值后面允许出现逗号
5.  Reserved words as property names 对象属性名可以使用保留字、关键字

## 1.get&amp;set 访问器

get&amp;set 一种获得属性值的方法，另一种设置属性值的方法，并且有自己的使用语法，可以对属性值进行预处理。
<pre>var employee = {
	set age(s){ //有且只能传递一个参数
		this._age = parseInt(s); //将字符串转换成整数
	},
	get age(){ //不能传递任何参数
		return this._age;
	}
}
employee.age = "24岁"; 
console.log(employee.age); //返回数字24
</pre>
这条扩展使用非常多，如下图，canvas绘图API上的原型属性。

[![2016-07-16_113801](http://www.mddup.com/wp-content/uploads/2016/05/2016-07-16_113801.png)](http://www.mddup.com/wp-content/uploads/2016/05/2016-07-16_113801.png)

## 2.对象&amp;数组字面量最后一个属性后面允许出现逗号

以前复制属性代码时，要去掉最后一个逗号，如果需要再添加属性，又得重新再加上，现在都不必那么麻烦了，相当于增强了JavaScript的容错机制。
<pre>var employees = [
	{
		name:"Adun",
		age:"24",
	},
	{
		name:"Fenix",
		age:"26",
	},
]
</pre>

## 3.对象属性名可以使用保留字、关键字

下面这个语法没问题，但估计也没多少人会这样干吧...
<pre>var obj = {
	var:10, //var是关键字
	class:20, //class是保留字
}
console.log(obj.var + obj.class) //30
</pre>
参考资料：[http://kangax.github.io/compat-table/es5/#es5shim](http://kangax.github.io/compat-table/es5/#es5shim)