---
title: JavaScript进阶知识点--JS变量与作用域
date: 2019-09-13 09:49:54
tags: JavaScript
categories: JavaScript
---
---

# 检测引用类型

## instanceof 方法（P88）

### 语法

```
    if(value instanceof Array){
        // 对数组执行某些操作
    }
```

# 变量

基本类型|引用类型
-|-
不可修改|可以修改
保存在栈内存中|保存在堆内存中
按值访问|按引用访问
比较时，值相等即相等|比较时，同一引用才相等
复制时，创建一个副本|复制的其实是指针
按值传递参数|按值传递参数
用 typeof 检测类型|用 instanceof 检测类型

# 延长作用域链（不推荐使用）（P75）

## with 方法

## try-catch 语句的 catch 块

# 垃圾收集（P79）

+ 标识清除

+ 引用计数（基本废除）

引用计数会在循环引用过程中出现错误

## 手动清除内存

将变量设置为 null