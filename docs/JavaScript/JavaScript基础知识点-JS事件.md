---
title: JavaScript基础知识点--JS事件
date: 2019-08-31 18:07:37
tags: JavaScript
categories: JavaScript
---
---

# JS事件

## 什么是事件

事件是可以被 JavaScript 侦测到的行为，通俗的讲就是当用户与 Web 页面进行某些交互时，解释器就会创建响应的 event 对象以描述事件信息

## 关于事件

常见的事件有：

+ 用户点击页面上的某项内容

+ 鼠标经过特定的元素

+ 用户按下键盘上的某个按键

+ 用户滚动窗口或改变窗口大小

+ 页面元素加载完成或加载失败

[JS事件列表](http://file.mukewang.com/class/assist/777/6616789/aob2e0gqewj/js%E4%BA%8B%E4%BB%B6%E5%88%97%E8%A1%A8%EF%BC%88%E6%95%99%E8%BE%85%EF%BC%89.pdf)

## 事件句柄

事件句柄（又称事件处理函数、事件监听函数），指用于响应某个事件而调用的函数。每一个事件均对应一个事件句柄，在程序执行时，将相应的函数或语句指定给事件句柄，则在该事件发生时，浏览器便执行指定的函数或语句

# 事件定义

为特定事件定义监听函数有三种方式：

1. 直接在 HTML 中定义元素的事件相关属性

    [具体写法及语法请参照该链接](https://youchen12138.github.io/2019/08/25/JavaScript%E5%9F%BA%E7%A1%80%E7%9F%A5%E8%AF%86%E7%82%B9-DOM%E4%BA%8B%E4%BB%B6/)

    缺点：违反了“内容与行为相分离”的原则，应尽可能少用

2. DOM 0级事件

    [具体写法及语法请参照该链接](https://youchen12138.github.io/2019/08/25/JavaScript%E5%9F%BA%E7%A1%80%E7%9F%A5%E8%AF%86%E7%82%B9-DOM%E4%BA%8B%E4%BB%B6/)

    优点：松耦合

    缺点：元素最多绑定一个事件

3. DOM 2级事件

    高级事件处理方式，一个事件可以绑定多个监听函数

    ```
        btn.addEventListener("click", function(){}, flase)// DOM
        btn.attachEvent("onclick", function(){})// IE
        document.body.addEventListener("load", init)
        document.body.attachEvent("onload", init)
        function init(){//...}
    ```

    此语法可以为一个元素绑定多个监听函数，但需要注意浏览器兼容问题

    优点：松耦合，绑定多个事件，事件捕获和事件冒泡

# DOM事件流

## 添加事件

### 语法

> Element.addEventListener(event，function，useCapture)

### 功能

用于向指定元素添加事件句柄

### 参数说明

+ event：必选项。字符串，指定事件名

+ function：必选项。指定要事件触发时执行的函数

+ useCapture：可选。布尔值，指定事件是否在捕获或冒泡阶段执行。false为事件冒泡，true为事件捕获。默认false

## 移除事件

### 语法

> Element.removeEventListener(event, function, useCapture)

### 功能

移除 addEventListener() 方法添加的事件句柄

### 参数说明

+ event：必选项。字符串，要移除的事件名称

+ function：必选项。指定要移除的函数

+ useCapture：可选。布尔值，指定移除事件句柄的阶段。alse为事件冒泡，true为事件捕获。默认false

### 注意

事件解绑成功的主要原因就是：保持 addEventListener() 和 removeEventListener() 的里面的参数一致

# IE事件流（IE事件处理程序）

只能适用于IE8及IE8以下的浏览器，执行顺序为事件冒泡

## 添加事件

### 语法

> Element.attachEvent(event, function)

### 功能

用于向指定元素添加事件句柄

### 参数说明

+ event：必选项。字符串，指定事件名，必须加“on”前缀

+ function：必选项。指定要事件触发时执行的函数

## 移除事件

### 语法

> Element.detachEvent(event, function)

### 功能

移除 attachEvent() 方法添加的事件句柄

### 参数说明

+ event：必选项。字符串，要移除的事件名称

+ function：必选项。指定要移除的函数

# 事件周期

解释器创建一个 event 对象后，会按如下过程将其在 HTML 元素间进行传播

第一阶段：事件捕获，事件对象沿 DOM 树向下传播

第二阶段：目标触发，运行事件监听函数

第三阶段：事件冒泡，事件沿 DOM 树向上传播

注意：IE 的事件模型中没有“事件捕获”阶段

## 事件冒泡

事件冒泡：直系亲属树结构中，点击某个元素，由于冒泡作用，亲属树上的元素凡是添加了事件的，都会被触发，触发顺序为从下到上

## 事件捕获

事件冒泡：直系亲属树结构中，点击某个元素，亲属树上的元素凡是添加了事件的，都会被触发，触发顺序为从上到下

## 事件委托（原理是事件冒泡）

+ 事件委托就是利用冒泡的原理，把事件加到父级上，触发执行效果。

+ 使用事件委托可以提高性能