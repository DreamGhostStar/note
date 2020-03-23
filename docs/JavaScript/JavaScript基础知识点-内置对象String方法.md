---
title: JavaScript基础知识点--内置对象String方法
date: 2019-08-23 17:39:25
tags: JavaScript
categories: JavaScript
---
---

# charAt()

## 语法

> stringObject.charAt(index)

## 功能

返回 stringObject 中 index 位置的字符

# charCodeAt()

## 语法

> stringObject.charCodeAt(index)

## 功能

返回 stringObject 中 index 位置的字符的编码

# indexOf

## 语法

> stringObject.indexOf("o");

## 功能

从一个字符串中搜索给定的子字符串，返回子字符串的位置，从前往后搜

## 返回值

数值

说明：如果没有找到该子字符串，这返回-1

# lastIndexOf

## 语法

> stringObject.lastIndexOf("o");

## 功能

从一个字符串中搜索给定的子字符串，返回子字符串的位置，从后往前搜

## 返回值

数值

说明：如果没有找到该子字符串，这返回-1

# 截取方法

## slice()

### 语法

> stringObject.slice(start, end);

### 功能

截取子字符串

### 参数说明

1. start：必需。指定子字符串的开始位置

2. end：可选。表示子字符串到哪里结束，end本身不在截取范围之内

3. 当参数为负数时，会将传入的负值与字符串的长度相加

## substring()

说明及功能同 slice() 完全一样

### 区别

1. 当参数为负数时，自动将参数转换为 0

2. substring()会将较小的数作为开始位置，将较大的数作为结束位置

## substr()

### 语法

> stringObject.substr(start, len)

### 功能

截取子字符串

### 参数说明

1. start：必需。指定子字符串的开始位

2. len：可选。表示截取的字符总数，省略时截取至字符串的末尾

3. 当 start 为负数，会将传入的负值与字符串的长度相加

4. 当 len 为负数时，返回空字符串

# 字符串转换为数组

## split()

### 语法

> stringObject.split(separator)

### 功能

把一个字符串分割成字符串数组

### 返回值

数组

### 说明

separator：必需。分隔符

# 字符串替换

## replace()

### 语法

> stringObject(regexp/substr, replacement)

### 功能

在字符串中用一些字符替换另一些字符，或替换一个与正则表达式匹配的子串

### 返回值

String

### 参数说明

regexp：必需。规定子字符串或要替换的模式的 RegExp 对象

replacement：必需。一个字符串值

# 转换大小写的方法

1. toUpperCase()

2. toLowerCase()

3. 将

## toUpperCase()

### 语法

> stringObject.toUpperCase()

### 功能

将字符串转换为大写

## toLowerCase()

### 语法

> stringObject.toLowerCase()

### 功能

把字符串转换为小写