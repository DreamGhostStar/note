---
title: JavaScript基础知识点--BOM基础及window对象
date: 2019-08-25 16:41:38
tags: JavaScript
categories: JavaScript
---
---

# 什么是 BOM

BOM（browser object model）浏览器对象模型

## BOM 对象

+ window

+ navigator

+ screen

+ history

+ location

+ document

+ event

# window

window 是浏览器的一个实例，在浏览器中，window 对象有双重角色，它既是通过 JavaScript访问浏览器窗口的一个接口，又是 ECMAScript 规定的 Global 对象

所有全局变量和全局方法都被归在 window 对象上

## window 对象方法

### alert

#### 语法

> window.alert("content")

#### 功能

显示带有一段消息和一个确认按钮的警告框

### confirm

#### 语法

> window.confirm("message")

##### 功能

显示一个带有指定消息和 OK 及取消按钮的对话框

##### 返回值

+ 如果用户点击确定按钮，则 confirm()返回 true

+ 如果用户点击取消按钮，则 confirm()返回 false

### prompt

#### 语法

> window.prompt("text, defaultText")

#### 参数说明

+ text：要在对话框中显示的纯文本（而不是 HTML 格式的文本）

+ defaultText：默认的输入文本

#### 返回值

+ 如果用户单击提示框的取消按钮，则返回 null

+ 如果用户单击确认按钮，则返回输入字段当前显示的文本

### open

#### 语法

> window.open(pageURL, name, parameters)

#### 功能

打开一个新的浏览器窗口或查找一个已命名的窗口

#### 参数说明

+ pageURL：子窗口路径

+ name：子窗口句柄（name 声明了新窗口的名称，方便后期通过 name 对子窗口进行引用）

+ parameters：窗口参数（各参数用逗号分隔）

##### 参数parameters说明

可选参数|说明
-|-
width|窗口宽度
height|窗口高度
left|窗口X轴坐标
top|窗口Y轴坐标
toolbar|是否显示浏览器的工具栏
menubar|是否显示菜单栏
scrollbars|是否显示滚动条
location|是否显示地址字段
status|是否添加状态栏

### close

#### 语法

> window.close()

#### 功能

关闭浏览器窗口

# 超时调用

## 语法

> setTimeout(code, millisec)

## 功能

在指定的毫秒数后调用函数或计算表达式

## 参数说明：

+ code：要调用的函数或要执行的 JavaScript 代码串

+ millisec：在执行代码前需等待的毫秒数

## 返回值

该方法返回一个 ID 值，通过它取消超时调用

# 清除超时调用

## 语法

> clearTimeout(id_of_settimeout)

## 功能

取消由 setTimeout() 方法设置的 timeout

## 参数说明

+ id_of_settimeout：由 setTimeout() 返回的 ID 值，该值标识要取消的延迟执行代码块

# 间歇调用

## 语法

> setInterval(code, millisec)

## 功能

每隔指定的时间执行一次代码

+ code：要调用的函数或要执行的代码串

+ millsec：周期性执行或调用 code 之间的时间间隔，以毫秒计

# 清除间歇调用

## 语法

> clearInterval(id_of_setinterval)

## 功能

取消 setInterval() 方法设置的 interval

## 参数说明：

+ id_of_setinterval：由 setInterval() 返回的 ID 值