---
title: JavaScript进阶知识点--JS函数深入
date: 2019-09-14 10:38:33
tags: JavaScript
categories: JavaScript
---
---

# 对象

## 创建对象（P145）

1. 字面量方法

2. 构造函数

3. `Object.create()`

## 删除对象属性

> delete obj.attributeName

## 检测属性是否在对象中

> attributeName in obj

例：

```
    var person = {
        name: "Tom"
    }

    console.log(name in person);// true
```

## 对象枚举

### for in 循环（P57）

# 函数

## 字面量

+ function 声明

+ var 赋值表达式

### 区别

var 赋值表达式不能写在调用之后

var 赋值表达式要先定义，后调用

## 构造函数（不建议）

例：

```
    var fun = new Function("num1", "num2", "return num1 + num2")
```

## 直接函数调用

+ 普通函数调用

+ 匿名函数调用（不能让function打头）（也叫自执行函数）

## 间接函数调用

+ fun.call()

+ fun.apply();

### 参数

1. 第一个参数：改变this的指向

2. 第二个参数：改变参数的值

    + call：传进的参数以逗号分隔

    + apply：传进的参数以数组形式体现

例：

```
    // call 方法调用
    fun.call(window, 1, 2);

    // apply 方法调用
    fun,apply(window, [1, 2]);
```

# 注意

+ 如果用 alert 或 document.write 输出不是字符串的值，则该值则调用 `toString()` 方法

+ document.write 期望接收和输出字符串，当接收的参数不为字符串时，会调用参数的`toString`方法，将其转化成字符串输出

+ 数组调用`toString()`后，会将其中的元素用逗号拼接起来变成字符串

+ 一般的对象调用toString()后返回`[object Object]`