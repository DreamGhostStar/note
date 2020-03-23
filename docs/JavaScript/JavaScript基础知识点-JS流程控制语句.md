---
title: JavaScript基础知识点--JS流程控制语句
date: 2019-08-22 17:13:57
tags: JavaScript
categories: JavaScript
---
---

# prompt()

## 语法

> prompt()

括号中的值提示用户输入

## 功能

弹出输入框

## 返回值

1. 点击确定，返回输入内容

2. 点击取消，返回 null

# length

## 语法

> string.length

## 功能

获取 string 字符串的长度

## 返回值

number

# 获取星期

## 语法

> new Date().getDay()

## 功能

获取当前时间的星期几

## 返回值

number(0-6)

# 输出

## 语法

> document.write("内容")

## 功能

向浏览器输出内容

# arguments

ECMAScript 中的参数在内部用一个数组来表示

在函数体内通过 arguments 对象来访问这个数组参数

说明：

1. arguments 对象只是与数组类似，并不是 Array 的实例

2. `[]` 语法访问它的每一个元素

3. length 属性确定传递参数的个数