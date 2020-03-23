---
title: JavaScript基础知识点--初识DOM
date: 2019-08-24 16:42:41
tags: JavaScript
categories: JavaScript
---
---

# JavaScript DOM 基础

DOM 是 Document Object Model（文档对象模型）的缩写

文档对象模型（DOM）是 HTML 和 XML 文档的编程接口，它提供了对文档的结构化的表述，并定义了一种方式可以使从程序中对该结构进行访问，从而改变文档的结构、样式和内容

# DOM 查找方法

## getElementById

### 语法

> document.getElementById("id")

### 功能

返回对拥有指定 ID 的第一个对象的引用

### 返回值

DOM 对象

### 说明

id 为 DOM 元素上 id 属性的值

## getElementsByTagName

### 语法

> document.getElementsByTagName("tag")

### 功能

返回一个对所有 tag 标签引用的集合

### 返回值

数组

### 说明

tag 为要获取的标签名称

# 设置元素样式

## 语法

> ele.style.styleName=styleValue

## 功能

设置 ele 元素的 CSS 样式

## 参数说明：

1. ele 为要设置样式的 DOM 对象

2. styleName 为要设置的样式名称，不能使用"-"连字符形式 font-size，使用驼峰命名形式 fontSize

3. styleValue 为设置的样式值

# innerHTML

## 语法

> ele.innerHTML

### 功能

返回 ele 元素开始和结束标签之间的 HTML

## 语法

> ele.innerHTML="html"

### 功能

设置 ele 元素开始和结束标签之间的 HTML 内容为 html

# className

## 语法

> ele.className

### 功能

返回 ele 元素的 class 属性

## 语法

> ele.className="cls"

### 功能

设置 ele 元素的 class 属性为 cls

动态添加 class 替换为元素本身的 class

# 获取属性

## 语法

> ele.getAttribute("attribute");

## 功能

获取 ele 元素的 attribute 属性

## 说明：

1. ele 是要操作的 DOM 对象

2. attribute 是要获取的 HTML 属性（如：id、type）

3. 获取标签属性语法：DOM 对象.属性，如p.id

# 设置属性

## 语法

> ele.setAttribute("attribute", value);

## 功能

在 ele 元素的 attribute 属性设置属性值

## 说明：

1. ele 是要操作的 DOM 对象

2. attribute 是要获取的 HTML 属性（如：id、type）

3. value 为设置的 attribute 属性的值

4. 如果 value 是字符串，需加引号

# 删除属性

## 语法

> ele.removeAttribute("attribute")

## 功能

删除 ele 上的 attribute 属性

## 说明：

1. ele 是要操作的 DOM 对象

2. attribute 是要删除的属性名称