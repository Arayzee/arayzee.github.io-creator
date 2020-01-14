---
title: "HTML入门笔记1"
date: 2020-01-03T02:38:33+08:00
draft: false
---
## HTML 起源
HTML（超文本标记语言——HyperText Markup Language）是构成 Web 世界的一砖一瓦。它定义了网页内容的含义和结构。除 HTML 以外的其它技术则通常用来描述一个网页的表现与展示效果（如 CSS），或功能与行为（如 JavaScript）。

“超文本”（hypertext）是指连接单个网站内或多个网站间的网页的链接。链接是网络的一个基本方面。只要将内容上传到互联网，并将其与他人创建的页面相链接，你就成为了万维网的积极参与者。

HTML 使用“标记”（markup）来注明文本、图片和其他内容，以便于在 Web 浏览器中显示。HTML 标记包含一些特殊“元素”如 &#60;head&#62;，&#60;title&#62;，&#60;body&#62;，&#60;header&#62;，&#60;footer&#62;，&#60;article&#62;，&#60;section&#62;，&#60;p&#62;，&#60;div&#62;，&#60;span&#62;，&#60;img&#62;，&#60;aside&#62;，&#60;audio&#62;，&#60;canvas&#62;，&#60;datalist&#62;，&#60;details&#62;，&#60;embed&#62;，&#60;nav&#62;，&#60;output&#62;，&#60;progress&#62;，&#60;video&#62; 等等等等。

HTML 元素通过“标签”（tag）将文本从文档中引出，标签由在“&#60;”和“&#62;”中包裹的元素名组成，HTML 标签里的元素名不区分大小写。也就是说，它们可以用大写，小写或混合形式书写。例如，&#60;title&#62; 标签可以写成 &#60;Title&#62;，&#60;TITLE&#62; 或以任何其他方式。

HTML由Tim Berners-Lee于1990年创立，一直被用作WWW的信息表示语言。WWW（万维网——World Wide Web）是存储在Internet计算机中、数量巨大的文档的集合。这些文档称为页面，它是一种超文本(Hypertext)信息，可以用于描述超媒体。文本、图形、视频、音频等多媒体，称为超媒体(Hypermedia)。Web上的信息是由彼此关联的文档组成的，而使其连接在一起的是超链接(Hyperlink)。WWW的三大核心是HTML、HTTP、URL，有了WWW才有了上网（输入网址，看到网站）这一概念。

## HTML起手式
在VSCode中创建HTML文件，我们可以使用emmet语法输入`!`按Tab键快速创建HTML框架，如下：
```html
<!DOCTYPE html> <!-- 文档类型 -->
<html lang="en"> <!-- html标签，可声明语言，如中文zh-CN -->

<head>
    <meta charset="UTF-8"> <!-- 声明文件字符编码 -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0, maximum-scale=1.0, user-scalable=no"> <!-- 禁用缩放，兼容手机 -->
    <meta http-equiv="X-UA-Compatible" content="ie=edge"> <!-- 告诉IE使用最新内核 -->
    <title>Document</title> <!-- 标题 -->
</head>

<body>

</body>

</html>
```

## HTML章节标签
* 标题 h1~h6
* 章节 section
* 文章 article
* 段落 p
* 头部 header
* 脚部 footer
* 主要内容 main
* 旁支内容 aside
* 划分 div

## HTML全局属性
HTML所有标签都具有的属性：
* class 类名
* contenteditable 内容是否可编辑
* hidden 是否隐藏
* id 唯一标识符
* style 样式
* tabindex 声明用户使用tab浏览时的顺序
* title 完整内容

## 常用内容标签
* ol + li 有序列表
* ul + li 无序列表
* dl + dt + dd 描述信息
* pre 预格式化
* hr 分割线
* br 换行
* a 链接
* em 斜体强调
* strong 粗体强调
* code 代码块
* q 引用
* blockquote 块级引用