---
title: "HTML常用标签"
date: 2020-01-15T13:27:08+08:00
categories: ["前端"]
tags: ["HTML"]
draft: false
---

# a标签
&lt;a&gt;可以创建通向其他网页、文件、同一页面内的位置、电子邮件地址或任何其他 URL 的超链接。常用属性有：herf、target。
## herf
herf有以下几种取值：
### 网址
* 以`http://`、`https://`等协议开头的网址，如[http://google.com](http://google.com)。
* 以`//`开头的网址，如[//google.com](http://google.com)，该写法会继承当前网址的协议。
### 路径
* 可使用相对路径或绝对路径，如`a/b/c`、`/a/b/c`，注意不要直接双击打开html文件，因为这样打开时，绝对路径会定位到当前盘符的根目录而非html服务的根目录。
* 若文件在当前目录下，可直接写文件名。
### 伪协议
* `javascript:代码;`点击a标签后将执行写入的代码。常用`javascript:;`来实现点击a标签后不采取操作的效果。
* `mailto:邮箱` 点击a标签后向指定邮箱发送邮件。
* `tel:手机号` 点击a标签后向指定号码拨号。
### id
* `#id` 点击a标签后跳转到页面中拥有该id的元素的位置。
## target
target有2种取值：
### 内置名字
* `_blank` 在新标签页打开。
* `_top` 在iframe的顶层打开。
* `_parent` 在iframe的父级打开。
* `_self` 在iframe自身打开。
### 程序员命名
* `window的name` 在指定名称的窗口打开。
* `iframe的name` 在指定名称的iframe打开。
# img标签
&lt;img&gt;能发出get请求，展示一张图片
## 常用属性
* `src` **必须**，包含了你想嵌入的图片的文件路径。
* `alt` 包含一条对图像的文本描述，这不是强制性的，但对可访问性而言，它难以置信地有用——屏幕阅读器会将这些描述读给需要使用阅读器的使用者听，让他们知道图像的含义。如果由于某种原因无法加载图像，普通浏览器也会在页面上显示alt属性中的备用文本：例如，网络错误、内容被屏蔽或链接过期时。
* `width,height` 设置原始分辨率：这将设置图像应占用的空间，以确保图像被加载之前页面的布局是稳定的。
## 常用事件
* `onload` 图片加载完毕后立即触发。
* `onerror` 加载或渲染图像时发生错误时触发。
## 响应式
移动端img标签应设置样式`max-width: 100%`以确保图片会自适应屏幕宽度。
# table标签
## 基本结构
例：
姓名|年龄
:-:|:-:
小红|19
小蓝|21
代码：
```html
<table>
  <thead>
    <tr>
      <th>姓名</th>
      <th>年龄</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>小红</td>
      <td>19</td>
    </tr>
    <tr>
      <td>小蓝</td>
      <td>21</td>
    </tr>
  </tbody>
  <tfoot>
  </tfoot>
</table>
```
## 相关样式
* `table-layout` 定义了用于布局表格单元格，行和列的算法。取值有：
   * `auto`  大多数浏览器采用自动表格布局算法对表格布局。表格及单元格的宽度取决于其包含的内容。
   * `fixed` 表格和列的宽度通过表格的宽度来设置，某一列的宽度仅由该列首行的单元格决定。在当前列中，该单元格所在行之后的行并不会影响整个列宽。
* `border-collapse` 用来决定表格的边框是分开的还是合并的。在分隔模式下，相邻的单元格都拥有独立的边框。在合并模式下，相邻单元格共享边框。取值有：
   * `separate` **默认值**，每个单元格拥有独立的边框。
   * `collapse` 相邻的单元格共用同一条边框。
* `border-spacing` 设置单元格之间的间隙，仅在border-collapse为separate时生效。