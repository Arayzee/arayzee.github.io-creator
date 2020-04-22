---
title: "jQuery基础"
date: 2020-04-22T21:58:39+08:00
categories: ["前端"]
tags: ["JS", "tech"]
draft: false
---

jQuery作为前端最长寿的库迄今为止已经存在了14年了，或许它早该过时，可实际上目前仍有80%左右的网站使用着jQuery。时间与用户证明了jQuery的可靠性，其优雅的设计模式与简洁的代码依然值得今天的我们学习。

---

# jQuery 如何获取元素

"选择某个网页元素，然后对其进行某种操作"是jQuery的基本设计思想和主要用法。

把选择表达式传入jQuery构造函数，然后将得到封装好API的被选中元素的jQuery对象。

选择表达式可以是CSS选择器：

```javascript
$(document) //选择整个文档对象

$('#myId') //选择ID为myId的网页元素

$('div.myClass') // 选择class为myClass的div元素

$('input[name=first]') // 选择name属性等于first的input元素
```

也可以是jQuery特有表达式：

```javascript
$('a:first') //选择网页中第一个a元素

$('tr:odd') //选择表格的奇数行

$('#myForm :input') // 选择表单中的input元素

$('div:visible') //选择可见的div元素

$('div:gt(2)') // 选择所有的div元素，除了前三个

$('div:animated') // 选择当前处于动画状态的div元素
```

此外，jQuery还支持改变结果集，通过强大的过滤器来对结果进行筛选、移动：

```javascript
筛选：

$('div').has('p'); // 选择包含p元素的div元素

$('div').not('.myClass'); //选择class不等于myClass的div元素

$('div').filter('.myClass'); //选择class等于myClass的div元素

$('div').first(); //选择第1个div元素

$('div').eq(5); //选择第6个div元素

移动：

$('div').next('p'); //选择div元素后面的第一个p元素

$('div').parent(); //选择div元素的父元素

$('div').closest('form'); //选择离div最近的那个form父元素

$('div').children(); //选择div的所有子元素

$('div').siblings(); //选择div的同级元素
```

---

# jQuery链式操作

jQuery最令人称道的一点就是链式操作，其原理为在每一步操作后返回一个jQuery对象，使得每一步操作可以连在一起，看似简单却体现了jQuery设计模式的简洁与优雅。

示例代码：

```javascript
$('div')

　.find('h3')

　.eq(2)

　.html('Hello')

　.end() //退回到选中所有的h3元素的那一步

　.eq(0) //选中第一个h3元素

　.html('World'); //将它的内容改为World
```
---

# jQuery 常用API

### 创建元素

> append() - 在被选元素的结尾插入内容<br>
prepend() - 在被选元素的开头插入内容<br>
after() - 在被选元素之后插入内容<br>
before() - 在被选元素之前插入内容

### 移动元素

> a.insertAfter(b) - 把a元素移动到b元素后面<br>
b.after(a) - 把b元素加到a元素前面<br><br>
表面上看，这两种方法的效果是一样的，唯一的不同似乎只是操作视角的不同。但是实际上，它们有一个重大差别，那就是返回的元素不一样。第一种方法返回div元素，第二种方法返回p元素。

### 完整文档

完整文档可访问 [jQuery中文文档](https://www.jquery123.com/)

---

本文部分内容参考自 [jQuery设计思想——阮一峰](http://www.ruanyifeng.com/blog/2011/07/jquery_fundamentals.html)
