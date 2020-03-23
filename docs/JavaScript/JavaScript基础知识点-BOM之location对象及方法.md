---
title: JavaScript基础知识点--BOM之location对象及方法
date: 2019-08-26 16:05:35
tags: JavaScript
categories: JavaScript
---
---

# location 对象

location 对象提供了与当前窗口中加载的文档有关的信息，还提供了一些导航的功能，它既是 window 对象的属性，也是 document 对象的属性

# location 对象的常用属性

## href

#3# 语法

> location.href

###n 功能

返回当前加载页面的完整URL

### 说明

location.href 与 window.location.href 等价

## hash

### 语法

> location.hash

### 功能

返回 URL 中的 hash（#号后跟零或多个字符），如果不包含这返回空字符串

### 说明

如果写了 location.hash=#xxx 相当于为当前对象设置锚点

如果未写，相当于为当前页面返回 URL 中的 #xxx

## host

### 语法

> location.host

### 功能

返回服务器名称和端口号

## hostname

### 语法

> location.hostname

### 功能

返回不带端口号的服务器名称

## pathname

### 语法

> location.pathname

### 功能

返回 URL 中的目录和（或）文件名

## port

### 语法

> location.port

### 功能

返回 URL 中指定的端口号，如果没有，返回空字符串

## protocol

### 语法

> location.protocol

### 功能

返回页面使用的协议

## search

### 语法

> location.search

### 功能

返回 URL 的查询字符串。这个字符串以问号开头

# 位置操作

## 改变浏览器位置的方法：

location.href 属性

## location 对象其他属性也可改变 URL

+ location.hash

+ location.search

## replace()

### 语法

> location.replace(url)

### 功能

重新定向 URL

### 说明

使用 location.replace 不会在历史记录中生成新记录

## reload()

### 语法

> location.reload()

### 功能

重新加载当前显示的页面

### 说明

+ location.reload()有可能从缓存中加载

+ location.reload(true)从服务器重新加载