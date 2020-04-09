---
title: "JavaScript 的诞生"
date: 2020-02-07T14:53:47+08:00
categories: ["前端"]
tags: ["JS", "other"]
draft: false
---

# 缘起

1995年之前，浏览器正如其名，只具备浏览网页的功能，所有交互都需要通过服务器来进行，以当时的网络状况，这一过程可能需要几十秒。即便是最简单的表单验证，也需要等服务器长时间的反复响应，用户体验有多糟糕可想而知。随着网上冲浪的人数越来越多，亟需一种网页脚本语言来解决这一现状。凭借Navigator浏览器而名声鹊起的网景公司（Netscape）看到了这一机遇，决定开发一种网页脚本语言。当时Sun公司正大肆宣扬自家的Java语言，并许诺这种语言可以"一次编写，到处运行"，它看上去很可能成为未来的主宰。于是网景决定与Sun结盟，这就是为什么早期浏览器可以运行Java的原因，只是因为它使得网页过于复杂，所以后来不得不放弃。1995年5月，深受Java影响的网景公司做出了这样一个决策：未来的网页脚本语言必须"看上去与Java足够相似"，但是比Java简单，使得非专业的网页作者也能很快上手。34岁的系统程序员Brendan Eich临危受命，担任了这一语言的设计师，Javascript应运而生。

图为Navigator浏览器1.0版：
![Navigator浏览器1.0版](/images/tooj/01.jpg)

# 祸根

## 玩具语言的自我修养

虽说Brendan被任命为Javascript的设计师，但其本人对Java十分不感冒，同时网景对Javascript的要求很低，用来完成表单验证等简单操作就行了，为应付公司安排，Brendan仅花了10天时间设计Javascript，他的设计思路如下：

1. 借鉴C语言的基本语法
2. 借鉴Java语言的数据类型和内存管理
3. 借鉴Scheme语言，将函数提升到"第一等公民"（first class）的地位
4. 借鉴Self语言，使用基于原型（prototype）的继承机制

可以说起初Javascript只是一门玩具语言，Brendan万万没想到Javascript会发展为现在这一盛状。由于当时设计时间极短，导致Javascript很多细节考虑的不严谨，甚至连Brendan本人都这样评价自己的Javascript：

> "与其说我爱Javascript，不如说我恨它。它是C语言和Self语言一夜情的产物。十八世纪英国文学家约翰逊博士说得好：'它的优秀之处并非原创，它的原创之处并不优秀。'（the part that is good is not original, and the part that is original is not good.）"

## 网景之死

网景凭借Javascript把自己抬升到了一个新的高度，同期，微软为了对抗网景，推出了自家的JScript以及支持JScript的IE3浏览器。为了反击微软，网景决定为Javascript申请国际标准。1997年6月，第一个国际标准ECMA-262正式颁布。要知道，C语言问世将近20年之后，国际标准才颁布，过早的标准化使得Javascript还未来得及调整自身的缺陷就已早早定型，为Javascript留下了许多历史遗留问题。

可惜好景不长，微软将IE捆绑进Windows，为网景判下了死刑。网景虽然死了，但Javascript的故事还在继续。

# 方兴未艾

长期以来Javascript正如网景期望的那样完成着简单的脚本工作，页面开发都是由后端和设计师完成。直到2004年谷歌的Gmail在线网页发布，人们才意识到网页原来不只可以看新闻和图片。其使用的AJAX技术为世界打开了一扇名为“前端”的大门，也把Javascript再一次推上了风口浪尖。

2008年，谷歌搭载V8引擎的Chrome浏览器横空出世，IE的统治地位不再。得力于快如闪电的V8引擎，Javascript迎来了新的一轮爆发，Node.js、npm、React等技术层出不穷，空前的技术热潮让很多技术可能你刚听说就已经过时，不可谓不壮观。2015年，ECMAScript第六版发布，其带来的许多新特性也让Javascript愈发的有模有样。

如今，Javascript创造的价值已不可估量，虽然其有许多令人诟病之处，但只要合理的避开那些缺陷，Javascript仍不失为一款值得学习的语言。Javascript避坑指南——[《Javascript秘密花园》](http://bonsaiden.github.io/JavaScript-Garden/zh/)

---

本文部分内容参考自阮一峰博客：[Javascript诞生记](http://www.ruanyifeng.com/blog/2011/06/birth_of_javascript.html)