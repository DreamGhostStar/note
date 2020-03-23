---
title: JavaScript基础知识点--内置对象Date方法
date: 2019-08-24 09:00:19
tags: JavaScript
categories: JavaScript
---
---

# 创建一个日期对象

## 语法

> new date()

## 功能

创建一个日期时间对象

## 返回值

不传参的情况下，返回当前的日期时间对象

## 说明：

如果想根据特定的日期和时间创建日期对象，必须传入表示该日期的毫秒数或者是一组用逗号隔开的表示年月日时分秒的参数，年月日必须选，时分秒可选

# 获取年月日时分秒及星期的方法

方法|作用
-|-
getFullTear()|返回4位数的年份
getMonth()|返回日期中的月份，返回值为0~11
getDate()|返回月份中的某一天
getDay()|返回星期几，返回值为0~6
getHours()|返回小时
getMinutes()|返回分
getSeconds()|返回秒
getTime()|返回表示日期的毫秒数

# 设置年月日时分秒及星期的方法

方法|作用
-|-
setFullTear()|设置4位数的年份
setMonth()|设置日期中的月份，值为0~11
setDate()|设置月份中的某一天
setHours()|设置小时
setMinutes()|设置分
setSeconds()|设置秒
setTime()|设置表示日期的毫秒数，会改变整个日期