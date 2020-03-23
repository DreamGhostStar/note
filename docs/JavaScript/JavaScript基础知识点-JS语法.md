---
title: JavaScript基础知识点--JS语法
date: 2019-08-21 14:51:22
tags: JavaScript
categories: JavaScript
---
---

# JavaScript 的组成

完整的 JavaScript 是由 ECMAScript（语法）、Browser Object（DOM、BOM）（特性）组成

# JavaScript语法规则

+ 语句结束使用分号，如果省略，则由解析器确定语句的结尾

+ ECMAScript 中的一切（变量、函数名和操作符）都区分大小写

## JavaScript 中的标识符

1. 由字母、数字、下划线或美元符号组成

2. 不能以数字开头

3. 不能使用关键字、保留字等作为标识符

## 变量

ECMAScript 的变量是松散类型

松散类型：可以用来保存任何类型的数据

每个变量仅仅是一个用于保存值的占位符

说明：

1. 省略 var 声明的变量是全局变量

2. 不推荐省略 var 操作符来定义全局变量

# JavaScript 的数据类型

## 简单数据类型

+ Undefined

+ Null

+ Boolean

+ Number

+ String

Object 是复杂类型

ECMAScript6 新增了 symbol 数据类型

## undefined

undefined 类型只有一个值，即特殊的 undefined

## null

1. null 值表示一个空对象指针

2. 如果定义的变量准备在将来用于保存对象，那么最好将变量初始化为 null 而表示其他值

说明：undefined 值是派生自 null 值的，所以 undefined == null 的返回结果是 true

## Number

表示整数和浮点数

## NaN

即非数值，是一个很特殊的数值

说明：

1. 任何涉及 NaN 的操作（例如NaN/10）都会返回 NaN

2. NaN 与任何值都不相等，包括 NaN 本身

## String

String 类型用于表示由零或多个16位 Unicode 字符组成的字符序列，即字符串。字符串可以用双引号("")或单引号('')表示

## Boolean

只有两个值

+ true：真

+ flase：假

# 函数

## typeof

功能|检测变量类型
-|-
语法|typeof 变量或 typeof（变量）
返回值|string 类型，有可能是：string、number、boolean、object、undefined、function

## isNaN

### 语法

> isNaN(n)

### 功能

检测 n 是否是“非数值”

### 返回值

boolean

说明：isNaN() 对接收的数值，先尝试转换为数值，再检测是否为非数值

## String()与toString()

### 语法

> str.toString()

功能：将 str 转换为字符串

返回值：str 的一个副本

参数：数值、布尔值、对象和字符串

说明：在不知道要转换的值是不是 null 或 undefined 的情况下，还可以使用 String() 函数，它能够将任何类型的值转换为字符串

# 类型转换

1. 除 0 之外的所有数字，转换为布尔型都为 true

2. 除""之外的所有字符，转换为布尔型都为 true

3. null 和 undefined 转换为布尔型为 flase

# 比较操作符

==：相等，只比较值是否相等

===：全等，比较值的同时比较数据类型是否相等

!=: 不相等，比较值是否不相等

!==: 不全等，比较值的同时比较数据类型是否不相等

返回值：Boolean 

# 逻辑操作符

&&：与

||：或

！：非

## 逻辑与(&&)

如果有一个操作数是 undefined / null / NaN, 另一个为其他类型，则返回 undefined / null / NaN

注意：

1. 多个操作数时，当所有操作数都为真，则返回最后一个操作数。

2. 两个操作数时，如果第一个操作数隐式类型转化后为true，则返回下一个操作数；如果第一个操作数隐式类型转化后为false，则返回第一个操作数。

## 逻辑或(||)

说明：在有一个操作数表示布尔值的情况，逻辑或操作就不一定返回布尔值，此时它遵循以下规则

1. 如果第一个操作数隐式转换后为 true，则返回第一个操作数

2. 如果第一个操作数隐式转换后为 false，则返回第二个操作数

## 逻辑非(!)

说明：

1. 不论操作数是什么数据类型，返回值都是 Boolean

2. !!操作符可以得到操作数的布尔值