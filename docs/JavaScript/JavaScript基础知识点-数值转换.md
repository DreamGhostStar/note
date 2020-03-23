---
title: JavaScript基础知识点--数值转换
date: 2019-08-21 17:09:09
tags: JavaScript
categories: JavaScript
---
---

# 数值转换

有三个函数可以把非数值转换为数值：

1. Number()

2. parseInt()

3. parseFloat()

说明：

1. Number()可以用于任何数据类型

2. Number() 只能转换纯数值的字符串

2. parseInt() 和 parseFloat() 则专门用于把字符串转换成数值

## parseInt()

会忽略字符串前面的空格，直至找到第一个非空格字符

说明：

1. 参数必须是以数字或进制开头，如果以非数字开头，那么结果为 NaN

2. 这个函数提供第二个参数：转换时使用的基数（即多少进制）

## parseFloat()

从第一个字符开始解析每个字符，直至遇见一个无效的浮点数字符为止

说明：除了第一个小数点有效外，parseFloat() 与 parseInt() 的第二个区别在于它始终都会忽略前导的零

注：如果字符串中包含有效的十六进制格式，parseInt('0xf')将'0x'转换为相同大小的十进制数值，而 parseFloat('0x')只会输出 0