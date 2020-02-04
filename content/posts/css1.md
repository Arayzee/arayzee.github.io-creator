---
title: "CSS知识总结"
date: 2020-02-03T20:44:39+08:00
categories: ["前端"]
tags: ["CSS"]
draft: false
---

# 浏览器渲染原理

## 浏览器渲染过程

1. 根据HTML构建HTML树（DOM）
2. 根据CSS构建CSS树（CSSDOM）
3. 将两棵树合并成一颗渲染树（render tree）
4. Layout - 布局（文档流、盒模型、计算大小和位置）
5. Paint - 绘制（把边框颜色、文字颜色、阴影等画出来）
6. Compose - 合成（根据层叠关系展示画面）

三棵树示意图：

![三棵树示意图](/images/css1/01.png)

## 渲染完成后如何更新样式？

一般我们使用JS来更新样式，例如：
```javascript
div.style.background = 'blue'
div.style.display = 'none'
div.classList.add('blue')
div.remove()
```

当样式变更后，浏览器通过Layout - Paint - Compose三个步骤来更新样式，但并非所有样式变更都会触发完整的三步，例如`div.remove()`会触发完整的三步，`div.style.background = 'blue'`会跳过Layout，改变`transform`则会跳过Layout和Paint。

三种更新方式示意图：

![三种更新方式示意图](/images/css1/02.png)

对于样式变更会触发哪些步骤可查阅[https://csstriggers.com/](https://csstriggers.com/)

# CSS动画

css实现动画有两种方式：`transition`和`animation`

## transition

语法：transition: 属性名 时长 过渡方式 延迟

transition可以为两个状态补充中间帧。如果还有中间态，可以通过监听transitionend事件或者用setTimeout来实现，具体代码如下：
```html
<div class="wrapper">
  <div id="demo"></div>
  <button id=button>开始</button>
</div>
```
```css
#demo{
  width: 100px;
  height: 100px;
  border: 1px solid red;
  margin: 50px;
  transition: transform 1s linear;
}

#demo.b{
  transform: translateX(200px);
}
#demo.c{
  transform: translateX(200px) translateY(100px);
}
```
```javascript
button.onclick = ()=>{
  demo.classList.add('b')
  setTimeout(()=>{
    demo.classList.remove('b')
    demo.classList.add('c')
  },1000)
}
```

## animation

transition可以为两个状态补充中间帧形成过渡动画，而animation则可以自定义关键帧来实现高度自定义的动画效果。

使用animation首先得声明关键帧动画，语法有两种：

1. 使用`from` `to`，例如：
   * ```css
     @keyframes anim {
       from {
         transform: translateX(0%);
       }
       to {
         transform: translateX(50%);
       }
     }
     ```

2. 使用百分比，例如：
   * ```css
     @keyframes anim {
       0% {
         transform: translateX(0%);
       }
       50% {
         transform: translateX(50%);
       }
       100% {
         transform: translateX(100%);
       }
     }
     ```

声明关键帧动画后，使用`animation`可以为元素添加动画。

语法：animation: 时长 | 过渡方式 | 延迟 | 次数 | 方向 | 填充模式 | 是否暂停 | 动画名;
