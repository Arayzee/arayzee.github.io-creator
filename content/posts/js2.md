---
title: "JS对象基本用法"
date: 2020-04-10T09:40:13+08:00
categories: ["前端"]
tags: ["JS", "tech"]
draft: false
---

# 数据类型

## 七种数据类型

* number
* string
* bool
* symbol
* undefined
* null
* object

其中object是唯一一种复杂类型

## 五个falsy值

* '' (空字符串)
* 0
* NaN
* undefined
* null

---

# 对象

### 定义

* 无序的数据集合
* 键值对的集合

### 写法
```javascript
{
  'name': 'arayzee',
  'age': 17
}
```

### 细节
* 键名是字符串，不是标识符，可以包含任意字符
* 引号可以省略，省略后就只能写标识符
* **就算引号省略了，键名还是字符串**

## 声明对象的两种语法

1. `let obj = { 'name': 'arayzee', 'age': 17 }` 简略写法，**常用**
2. `let obj = new Object({ 'name': 'arayzee', 'age': 17 })` 完整写法

## 增 OR 改

* 直接赋值
  * `let obj = { 'name': 'arayzee' }`
  * `obj.name = 'arayzee'`
  * `obj['name'] = 'arayzee'`
  * `let key = 'name'; obj[key] = 'arayzee'`

* 批量赋值
  * `Object.assign(obj, {age: 17})`

**已有属性则改，没有属性则增**

### 修改或增加共有属性

* 无法通过自身修改或增加原型上的共有属性
* 可以通过__proto__修改原型上的属性，但是不推荐使用
* 不推荐使用__proto__修改原型，推荐使用Object.create，也就是说要定好原型后尽可能不要再修改

## 删

`delete obj.xxx` 或 `delete obj['xxx']`

## 查

* `Object.keys(obj)` 查对象自身属性
* `console.dir(obj)` 打印对象自身及原型上的属性
* `obj['xxx'], obj.xxx, obj[xxx](xxx为变量)` 查指定属性的值

## 'name' in obj 和 obj.hasOwnProperty('name') 的区别

`'name' in obj` 会在自身和原型上查找，而 `obj.hasOwnProperty('name')` 只会在自身查找