---
title: 我的javascript学习笔记
tags:
  - JavaScript
id: 52
categories:
  - WEB技术
---

1.  检测一个未声明的变量只能使用typeof运算符 `typeof str == "undefined";` //输出true
2.  在函数里的if语句有return表示符合则返回，return下面的语句就不执行
3.  currentStyle和getComputedStyle与padding不相关,
clientWidth和clientHeight当没有设置width和height时，ie6 ie7 返回0
scrollWidth和scrollWidth显示的是当有滚动条时，内容的实际大小
对象的offsetWidth和offsetHeight属性用来取得对象在页面中的实际所占区域大小  (所设置的宽高加边框加填充，当有滚动条时还会算上滚动条)
元素的offsetLeft与offsetTop属性返回元素在页面中相对于父元素的坐标。
scrollLeft和scrollTop,它们用来获得那些具有滚动条的元素滚动条滚动的距离
4.  页面重定向方法：`location.href;location.assign();location.replace();`
5.  执行一个全局函数，函数内部this指向window
6.  一个函数是哪个对象的方法，那么这个this就指向这个对象
7.  注释技巧:使用`if(false){被注释的语句}`来注释
8.  使用{}来表示一段代码块，{}本身并不会产生任何作用
9.  可以使用中文变量名 属性名 等 例如：`var 变量 = 100; alert(变量);` //输出100
10.  num = 123;//自动创建一个全局变量
function test() {
var a="Inner";//在函数中使用var声明变量 ，是局部变量
b="Gobal";//全局变量b
}
test();
alert(a);//不可以执行
alert(b);//可以执行
11.  判断非数字（或者能被转换为这样的值）使用`isNaN();`函数
12.  时间：注意东八区 `var d = new Date();`
`d.getMonth();`一月用0表示；`d.getDay();`星期一用1表示，星期日用0表示；
如果设置9月32号 `d.setMonth(10,32);` 就会自动跳到10月2号
13.  转义掉换行符：`var s = 'str\`
`ing';`    这样写是可以的
14.  类型转换：`toString(2)`里加参数表示用多少进制输出，例如：`var n = 8; alert(n.toString(2));`//输出1000
使用*1转换成Number类型，+''空字符串转为String类型，!!转为Boolean类型。
15.  `var obj = {};alert(obj);`//输出[object Object] 前面object表示类型typeof    后面Object是类
16.  奇怪的现象`var bool = new Boolean(false);alert(bool);alert(!bool);`//输出两次false

&nbsp;
<div class="alert alert-info">笔记中大部分记录的是学习ECMAscript语法部分，虽然比较枯燥无聊，但是也没办法，必须学的非常精通才行。因为哪怕是像jQuery这样优秀的js框架，也逃不出ECMAscript语法。至于BOM和DOM，因为jQuery封装的特别好，用jQuery的就行了，原生的DOM对象的属性方法就没必要去死记了。</div>

本笔记不定期更新... ...

//最新更新

new Date(Date.UTC(2010,5,5,10,10,10))

字符字面量无法添加属性，但可以使用内置的方法。
字符字面量当使用 instanceof 检查基本类型的值时，它会返回 false。
以上new String()正好相反

没有块级作用域
块级作用域表示诸如 if 语句等有花括号封闭的代码块，所以，支持条件判断来定义变
量。
if (true) { //if 语句代码块没有局部作用域
var box = 'Lee';
}
alert(box);
for 循环语句也是如此
for (var i = 0; i < 10; i ++) { //没有局部作用域
var box = 'Lee';
}
alert(i);
alert(box);
var 关键字在函数里的区别
function box(num1, num2) {
var sum = num1 + num2; //如果去掉 var 就是全局变量了
return sum;
}
alert(box(10,10));
alert(sum); //报错
PS：非常不建议不使用 var 就初始化变量，因为这种方法会导致各种意外发生。所以初
始化变量的时候一定要加上 var。

关于 this 的使用，this 其实就是代表当前作用域对象的引用。如果在全局范围 this 就代
表 window 对象，如果在构造函数体内，就代表当前的构造函数所声明的对象。

如果想要 box1 也能在后面继续访问到原型里的值，可以把构造函数里的属性删除即可，
具体如下：
delete box1.name; //删除属性
alert(box1.name);

第 15 章 面向对象与原型 纠错笔记
1.构造函数可以访问prototype属性

方括号语法的主要优点是可以通过变量来访问属性，例如：
var propertyName = "name";
alert(person[propertyName]); //"Nicholas"
如果属性名中包含会导致语法错误的字符，或者属性名使用的是关键字或保留字，也可以使用方括号表示法。例如：
person["first name"] = "Nicholas";
设置 innerText 永远只会生成当前节点的一个子文本节点，而为了确保只生成一个子文本节点，就必须要对文本进行 HTML 编码。利用这一点，可以通过 innerText 属性过滤掉 HTML 标签。方法是将 innerText 设置为等于 innerText，这样就可以去掉所有 HTML 标签，比如：div.innerText = div.innerText;
document.activeElement和document.hasFocus

ECMAScript 5 新增了 Array.isArray()方法

如果 this 在全局范围就是 window，如果在对象内部就指向这个对象。而闭包却
在运行时指向 window 的，因为闭包并不属于这个对象的属性或方法。

$(document).on('keydown',function(e){
if (e.ctrlKey && e.keyCode == 13) console.log('3') //判断按住了 ctrl 和 enter 键触发
})

style="ime-mode:disabled" //CSS禁止输入法

this.style[css] = value; //函数内的传值如果是对象属性，必须使用数组下标写法

!function (t){if(t !== undefined) alert(t)}(5)  //使用para !== undefined 来检测是否传递了para参数

//Jquery笔记
$('ul *') //选取UL下所有元素
$("p").eq(-2) //从集合中的最后一个元素开始倒数。(1算起)

UPDATE  `test`.`s` SET  `item` =  replace(`item`,'B','Z')  //替换数据库中的数据