---
title: JavaScript基础知识点--DOM事件
date: 2019-08-25 08:36:42
tags: JavaScript
categories: JavaScript
---
---

# 什么是事件

事件就是文档或浏览器窗口中发生的一些特定的交互瞬间

## HTML 事件

直接在 HTML 元素标签内添加事件，执行脚本

### 语法

> `<tag 事件="执行脚本"></tag>`

### 功能

在 HTML 元素上绑定事件

### 不建议使用 HTML 事件

1. 多元素绑定相同事件时，效率低

2. 不建议在 HTML 元素中写 JavaScript 代码

### 说明

执行脚本可以是一个函数的调用

## DOM 0级事件

1. 通过 DOM 获取 HTML 元素

2. （获取 HTML 元素）.事件 = 执行脚本

### 语法

> ele.事件 = 执行脚本

### 功能

在 DOM 对象上绑定事件

### 说明：

执行脚本可以是一个匿名函数，也可以是一个函数的调用

除非调用匿名函数，否则调用普通函数不能加括号

# 鼠标事件

事件名称|作用
-|-
onload|页面加载时触发
onclick|鼠标点击时触发
onmouseover|鼠标滑过时触发
onmouseout|鼠标离开时触发
onfocus|获得焦点时触发
onblur|失去焦点时触发
onchange|域的内容改变时发生
onsubmit|表单中的确认按钮被点击时发生，这个事件不是加在按钮上，而是表单上
onmousedown|鼠标按钮在元素上按下时触发
onmousemove|在鼠标指针移动是发生
onmouseup|在元素上松开鼠标按钮时触发
onresize|当调整浏览器窗口的大小时触发
onscroll|拖动滚动条滚动时触发
ondblclick|双击元素触发

onfocus 事件用于 input 标签 type 为 text、password 和 textarea 标签

# 键盘事件与 keyCode 属性

事件名称|作用
-|-
onkeydown|在用户按下一个键盘按键时发生
onkeypress|在按下键盘按键时发生（只会响应字母与数字符号）
onkeyup|在键盘按键被松开时发生
keyCode|返回 onkeypress、onkeydown 或 onkeyup 事件触发的键的值的字符代码，或键的代码
charCode|返回键的ASCll码
textInput|只有在可编辑区域，按下能够输入实际字符的键时才会触发此事件

## textInput 详解

### 第一种情况

输入框中按下enter键，触发的只有keypress事件

### 第二种情况

按下a键，触发keypress和textinput事件

## 键盘事件触发顺序

1. onkeydown

2. onkeypress

3. onkeyup

## event

event 代表事件的状态，如触发 event 对象的元素、鼠标的位置及状态等

## 获取按键的字符代码

```
document.onkeypress = function(event){
    console.log(event.keyCode);
}
```

## charCode与keyCode的区别

charCode 返回onkeypress事件触发键值的字母代码。

keyCode 返回 onkeydown 或 onkeyup 事件的键的代码。

# 其他事件

事件名称|触发条件
-|-
DOMNodeRemoved|Document 中任意元素被删除就会触发
DOMSubtreeModified|DOM结构中发生任何变化都会触发
DOMNodeRemoveFromDocument|从文档中移除之前会触发
DOMNodeInserted|Document 中任意元素被添加就会触发
DOMNodeInsertedIntoDocument|从文档中添加之前被触发

# HTML5新增的事件

事件名称|触发条件
-|-
DOMContentLoaded|在DOM树之后就会触发，不理会图像、JavaScript文件、CSS文件或其他资源是否已经下载。速度一定快于load事件
readystatechange|请参照下面的描述
hashchange|对象一定是window。#号后面的值变化时触发

## readystatechange 事件详解

提供文档或者元素加载过程，但很难预料与load事件一起使用时候

### 返回值

1. uninitialized：尚未初始化

2. loading：对象正在加载数据

3. interactive：可以操作对象，但还没有完全加载

4. 对象已经加载完毕

但其他资料并不是这样写的

请参照[菜鸟教程--readystatechange 事件](https://www.runoob.com/ajax/ajax-xmlhttprequest-onreadystatechange.html)

# 移动端常用的事件类型

事件类型名称|触发
-|-
touchstart|手指触摸屏幕
touchmove|手指在屏幕上滑动
touchend|手指从屏幕上移开


# 关于 this 指向

在事件触发的函数中，this 是对该 DOM 对象的引用