---
title: "JS基本语法"
date: 2020-04-09T13:25:30+08:00
categories: ["前端"]
tags: ["JS", "tech"]
draft: false
---

# 表达式和语句

通常表达式都会有值，而语句可能有可能没有。语句可以理解为一个行为，通常会改变环境（声明、赋值）。例如`1+2`、`add(1, 2)`、`console.log(3)`为表达式，`var a = 1`为语句。

JS中大部分空格、回车没有实际意义，但是`return`后面不能加回车。

**JS是大小写敏感的**

# 标识符的规则

标识符是用来识别具体对象的一个名称。最常见的标识符就是变量名，以及后面要提到的函数名。

* 第一个字符可以是Unicode字母或$或_或中文
* 后面的字符除了上述几种还可以是数字

# 条件语句

## if else 语句

当指定条件为真，if 语句会执行一段语句。如果条件为假，则执行另一段语句。

语法：

```javascript
if (condition)
   statement1
[else
   statement2]
```

`condition` 值为真或假的表达式

`statement1` 当condition为真时执行的语句。可为任意语句，包括更深层的内部if语句。要执行多条语句，使用块语句（{ ... }）将这些语句分组；若不想执行语句，则使用空语句。 

`statement2` 如果condition为假且 else从句存在时执行的语句。可为任意语句，包括块语句和嵌套的if语句。

多层 if...else 语句可使用 else if 从句。

## switch 语句

switch 语句评估一个表达式，将表达式的值与case子句匹配，并执行与该情况相关联的语句。

语法：

```javascript
switch (expression) {
  case value1:
    // 当 expression 的结果与 value1 匹配时，执行此处语句
    [break;]
  case value2:
    // 当 expression 的结果与 value2 匹配时，执行此处语句
    [break;]
  ...
  case valueN:
    // 当 expression 的结果与 valueN 匹配时，执行此处语句
    [break;]
  [default:
    // 如果 expression 与上面的 value 值都不匹配，执行此处语句
    [break;]]
}
```

`expression` 一个用来与 case 子语句匹配的表达式。

`case valueN (可选)` 用于匹配 expression 的 case 子句。如果 expression 与给定的 valueN 相匹配，则执行该 case 子句中的语句直到该 switch 语句结束或遇到一个 break 。

`default (可选)` 一个 default 子句；如果给定，这条子句会在 expression 的值与任一 case 语句均不匹配时执行。

## 其他

### 三元表达式

条件（三元）运算符是 JavaScript 仅有的使用三个操作数的运算符。一个条件后面会跟一个问号（?），如果条件为 truthy ，则问号后面的表达式A将会执行；表达式A后面跟着一个冒号（:），如果条件为 falsy ，则冒号后面的表达式B将会执行。本运算符经常作为 if 语句的简捷形式来使用。

语法：

```javascript
condition ? exprIfTrue : exprIfFalse
```

`condition` 计算结果用作条件的表达式。

`exprIfTrue` 如果表达式 condition 的计算结果是 truthy（它和 true 相等或者可以转换成 true ），那么表达式 exprIfTrue 将会被求值。

`exprIfFalse` 如果表达式 condition 的计算结果是 falsy（它可以转换成 false ），那么表达式 exprIfFalse 将会被执行。

### &&短路逻辑

`A&&B&&C&&D`取第一个假值或D，并不会取true/false。

### ||短路逻辑

`A||B||C||D`取第一个真值或D，并不会取true/false。

# 循环语句

## while 语句

while 语句可以在某个条件表达式为真的前提下，循环执行指定的一段代码，直到那个表达式不为真时结束循环。

语法：

```javascript
while (condition)
  statement
```

`condition` 条件表达式，在每次循环前被求值。如果求值为真，statement就会被执行。如果求值为假，则跳出while循环执行后面的语句。

`statement` 只要条件表达式求值为真，该语句就会一直被执行。要在循环中执行多条语句，可以使用块语句（{ ... }）包住多条语句。

## for 语句

for语句是while语句的语法糖。for 语句用于创建一个循环，它包含了三个可选的表达式，这三个表达式被包围在圆括号之中，使用分号分隔，后跟一个用于在循环中执行的语句（通常是一个块语句）。

语法：

```javascript
for ([initialization]; [condition]; [final-expression])
   statement
```

`initialization` 一个表达式 (包含赋值语句) 或者变量声明。典型地被用于初始化一个计数器。该表达式可以使用 var 或 let 关键字声明新的变量，使用 var 声明的变量不是该循环的局部变量，而是与 for 循环处在同样的作用域中。用 let 声明的变量是语句的局部变量。该表达式的结果无意义。

`condition` 一个条件表达式被用于确定每一次循环是否能被执行。如果该表达式的结果为 true，statement 将被执行。这个表达式是可选的。如果被忽略，那么就被认为永远为真。如果计算结果为假，那么执行流程将被跳到 for 语句结构后面的第一条语句。

`final-expression` 每次循环的最后都要执行的表达式。执行时机是在下一次 condition 的计算之前。通常被用于更新或者递增计数器变量。

`statement` 只要condition的结果为true就会被执行的语句。要在循环体内执行多条语句，使用一个块语句（{ ... }）来包含要执行的语句。没有任何语句要执行，使用一个空语句（;）。

## break 和 continue

break 语句中止当前循环，switch语句或label 语句，并把程序控制流转到紧接着被中止语句后面的语句。

continue 声明终止当前循环或标记循环的当前迭代中的语句执行，并在下一次迭代时继续执行循环。

continue 与 break 的区别在于， continue 并不会终止循环的迭代，而是：

* 在 while 循环中，控制流跳转回条件判断；
* 在 for 循环中，控制流跳转到更新语句。

## label

标记语句可以和 break 或 continue 语句一起使用。标记就是在一条语句前面加个可以引用的标识符（identifier）。

语法：

```javascript
label :
   statement
```

`label` 任何不属于保留关键字的 JavaScript 标识符。

`statement` JavaScript 语句。break 可用于任何标记语句，而 continue 可用于循环标记语句。

示例：

```javascript
var i, j;

    loop1:
    for (i = 0; i < 3; i++) {      //The first for statement is labeled "loop1"
       loop2:
       for (j = 0; j < 3; j++) {   //The second for statement is labeled "loop2"
          if (i === 1 && j === 1) {
             continue loop1;
          }
          console.log('i = ' + i + ', j = ' + j);
       }
    }

// Output is:
//   "i = 0, j = 0"
//   "i = 0, j = 1"
//   "i = 0, j = 2"
//   "i = 1, j = 0"
//   "i = 2, j = 0"
//   "i = 2, j = 1"
//   "i = 2, j = 2"
// Notice how it skips both "i = 1, j = 1" and "i = 1, j = 2"
```

**注意：**

```javascript
{
  foo: 1
}
```
上述代码不是一个对象，`foo`是label，内容为`1`。