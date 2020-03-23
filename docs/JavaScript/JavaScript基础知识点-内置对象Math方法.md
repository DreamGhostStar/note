---
title: JavaScript基础知识点--内置对象Math方法
date: 2019-08-24 07:48:37
tags: JavaScript
categories: JavaScript
---
---

# 求最大、最小值

## min()

### 语法

> Math.min(num1, num2...numN)

### 功能

求一组数中的最小值

### 返回值

Number

## max()

### 语法

> Math.max(num1, num2...numN)

### 功能

求一组数中的最大值

### 返回值

Number

# 取整方法

## ceil()

### 语法

> Math.ceil(num)

### 功能

向上取整，即返回大于 num 的最小整数

### 返回值

Number

## floor()

### 语法

> Math.floor(num)

### 功能

向下取整，即返回 num 的整数部分

### 返回值

Number

## round()

### 语法

> Math.round(num)

### 功能

将数值四舍五入为最接近的整数

### 返回值

Number

## abs()

### 语法

> Math.abs(num)

### 功能

返回 num 的绝对值

### 返回值

Number

# 产生随机数

## random()

### 语法

> Math.random()

### 功能

返回大于等于0小于1的一个随机数

### 返回值

Number

### 说明

求n到m之间的随机整数的公式

> random=Math.floor(Math.random()*(m-n+1)+n);