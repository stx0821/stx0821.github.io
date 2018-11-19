---
title: 如何去除Dreamweaver中的CSS widows属性提示
tags:
  - CSS
id: 57
categories:
  - WEB技术
---

CSS中有一个名叫`widows`的属性（注意不是windows），是一个设置打印的属性，设置当元素内部发生分页时必须在页面顶部保留的最少行数。只要涉及到打印方面的属性，我一般都会无视掉，因为大部分网站都不会专门去设置这个东西，我相信你也一样。
<!--more-->
本来是井水不犯河水的，但是平时使用Dreamweaver写样式代码时，写到设定`width`，这玩意就跳出来了，如下图[![2015-11-10_165250](http://www.mddup.com/wp-content/uploads/2015/11/2015-11-10_165250.png)](http://www.mddup.com/wp-content/uploads/2015/11/2015-11-10_165250.png)

`width`这个非常常用属性排在他后面，每次都得差不多打全才行，太烦人了，不删不行。

删除的办法其实很简单，找到并打开\Adobe Dreamweaver CS6\configuration\CodeHints\CodeHints.xml

[![2015-11-10_170635](http://www.mddup.com/wp-content/uploads/2015/11/2015-11-10_170635-300x29.png)](http://www.mddup.com/wp-content/uploads/2015/11/2015-11-10_170635.png)

大约在3441行，注释、删除或者和下面那行换行都行`&lt;menuitem label="widows" value="widows:" icon="shared/mm/images/hintMisc.gif" /&gt;`，然后重启Dreamweaver。

[![2015-11-10_170907](http://www.mddup.com/wp-content/uploads/2015/11/2015-11-10_170907.png)](http://www.mddup.com/wp-content/uploads/2015/11/2015-11-10_170907.png)

以后只要输入wi，代码就自动提示`width`了，是不是很方便呢![](/wp-content/themes/9IPHP-master/images/smilies/icon_rolleyes.gif)。
<div class="alert alert-warning">本人只测试了Dreamweaver CS6版本，其余低版本未测试。</div>

location.reload(true)可以强制刷新

document.referrer; //获取表单提交的上一个 URL，服务器端

DOM 提供了一些滚动页面的方法，如下：
document.getElementById('box').scrollIntoView(); //将指定的元素滚动到可见范围内