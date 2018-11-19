---
title: 使用百度URL实现搜索建议
tags:
  - JavaScript
id: 112
categories:
  - WEB技术
date: 2016-06-23 16:03:00
---

![封面](http://www.mddup.com/wp-content/uploads/2016/06/2016-06-24_121628.png)

很多时候由于我们自身的数据库数据量不够，或者其它原因导致不能很好的实现搜索建议，这个时候就可以考虑使用第三方返回的数据来实现。

我发现百度在实现搜索建议使用的并不是XHR对象，而是使用的JSONP来实现的，这样的话其它网站也可以随便向百度发送请求，得到自己想要的数据。我自己简单的实现了下，确实可行，服务器端并没有拒绝跨域的请求，效果如下：

![](http://www.mddup.com/wp-content/uploads/2016/06/jdfw.gif)
HTML代码：
<pre>
&lt;input id="bdinput" value=""&gt;
&lt;ul id="bdlist"&gt;
&lt;/ul&gt;
</pre>
Javascript代码：
<pre>$('#bdinput').on('keyup',function(e){	//这里不能用keydown和keypress，要不然就会先执行，再获取到值了，也就是说永远会少获取到一个值
	var jsonpCallback = 'jQuery' + Date.now();	//重置jsonp的回调函数名
	$.ajax({
		url:'https://sp0.baidu.com/5a1Fazu8AA54nxGko9WTAnF6hhy/su',	//百度的接受请求的URL
		dataType:'jsonp',	//类型必须是jsonp
		data:{
			wd:$(this).val(),	//传递搜索关键字
			cb:jsonpCallback	//传递jsonp的回调函数名
		},
		jsonpCallback:jsonpCallback,	//成功后的回调函数名，需要和服务器返回的保持一致
		success:function(d){
			$('#bdlist').empty();
			d.s.map(function(v,i,arr){	//将数据遍历并显示出来
				$('#bdlist').append('&lt;li&gt;'+ v +'&lt;/li&gt;');
			})
		}
	})
})
</pre>

**Demo地址：**[http://www.mddup.com/wp-content/uploads/demo/112.html](/wp-content/uploads/demo/112.html)
<iframe class="demoiframe" src="/wp-content/uploads/demo/112.html" height="320" seamless></iframe>