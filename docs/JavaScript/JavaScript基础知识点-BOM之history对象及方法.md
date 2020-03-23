---
title: JavaScript基础知识点--BOM之history对象及方法
date: 2019-08-26 18:35:17
tags: JavaScript
categories: JavaScript
---
---

# history 对象

history 对象保存了用户在浏览器中访问页面的历史记录

# history 对象方法

## back()

### 语法

> history.back()

### 功能

回到历史记录的上一步

### 说明

相当于使用了 history.go(-1)

## forward()

### 语法

> history.forward()

### 功能

回到历史记录的下一步

### 说明

相当于使用了 history.go(1)

## go(-n)

### 语法

> history.go(-n)

### 功能

回到历史记录的前n步

## go(n)

### 语法

> history.go(n)

### 功能

回到历史记录的后n步