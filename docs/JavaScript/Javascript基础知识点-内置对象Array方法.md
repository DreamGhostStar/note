---
title: Javascript基础知识点--内置对象 Array 方法
date: 2019-08-23 11:09:21
tags: Javascript
categories: JavaScript
---
---

# 数组的栈方法

1. push()

2. unshift()

3. pop()

4. shift()

## push()

### 语法

> arrayObject.push(newele1, newele2,...,neweleX)

### 功能

把它的参数顺序添加到 arrayObject 的尾部

### 返回值

把指定的值添加到数组后的新长度

## unshift()

### 语法

> arrayObject.unshift(newele1, newele2,...,neweleX)

### 功能

把它的参数顺序添加到 arrayObject 的开头

### 返回值

把指定的值添加到数组后的新长度

## pop()

### 语法

> arrayObject.pop()

### 功能

删除 arrayObject 的最后一个元素

### 返回值

被删除的那个元素

## shift()

### 语法

> arrayObject.shift()

### 功能

删除 arrayObject 的第一个元素

### 返回值

被删除的那个元素

# 数组的转换方法

## join()

### 语法

> arrayObject.join(separator)

### 功能

用于把数组中的所有元素放入一个字符串

### 返回值

字符串

### 说明

如果没有参数的话，默认用逗号连接。

如果有参数，用参数连接数组中的值来构成字符串

# 数组的重排序方法

## reverse()

### 语法

> arrayObject.reverse()

### 功能

用于颠倒数组中元素的顺序

### 返回值

数组

## sort()

### 语法

> arrayObject.sort(sortby)

### 功能

用于对数组的元素进行排序

### 返回值

数组

### 说明

1. 即使数组中的每一项都是数值，sort()方法比较的也是字符串

2. sort()方法可以接收一个比较函数作为参数

3. 参数中放置比较函数,[参考资料](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)

```
//降序
function(a, b){return b-a}

//升序
function(a, b){return a-b}
```

# 其他方法

## concat()

### 语法

> arrayObject.concat(arrayX, arrayX, arrayX,...,arrayX)

### 功能

用于连接两个或多个数组

### 返回值

数组

## slice()

### 语法

> arrayObject.slice(start, end)

### 功能

从已有的数组中返回选定的元素，原数组不变

截取从 start 到 end（不包含该元素）的元素，即从 start 到 end-1 的元素

### 参数说明

start（必需）规定从何处选取，如是负数，从数组尾部开始算起

end（可选）规定从何处结束选取，是数组片段结束处的数组下标，该下标对应的值不会被截取

说明：

1. 如果没指定 end，切分的数组包含从 start 到数组结束的所有元素

2. 如 slice()方法的参数中有一个负数，则用数组长度加上该数来确定相应的位置

### 返回值

数组

## splice()

### 删除

#### 语法

> arrayObject.splice(index, count)

#### 功能

删除从 index 处开始的零个或多个元素，原数组要变化

#### 返回值

含有被删除的元素的数组

#### 说明

count 是要删除的项目数量，如果设置为 0，则不会删除项目。

如果不设置，则删除从 index 开始的所有值

## 插入

### 语法

> arrayObject.splice(index, 0, item1,...,itemX)

### 功能

在指定位置插入值

### 参数

index：起始位置

0：删除的项数

item1...itemX：要插入的项

返回值：被删除的数组（如果没有删除，则返回空数组）

## 替换

### 语法

> arrayObject.splice(index, count, item1,...,itemX)

### 功能

在指定位置插入值，且同时删除任意数量的项

### 参数

index：起始位置

count：要删除的项

item1...itemX：要插入的项

返回值：从原始数组中删除的数，组成数组

# 位置方式

## indexOf()

### 语法

> arrayObject.indexOf(searchvalue, startIndex)

### 功能

从数组的开头（位置0）开始向后查找

### 参数

searchvalue：必需。要查找的项

startIndex：可选。起点位置的索引

### 返回值

number，查找的项在数组中的位置，没有找到的情况下返回-1

## lastIndexOf()

### 语法

> arrayObject.lastIndexOf(searchvalue, startIndex)

### 功能

从数组的末尾开始向前查找

### 参数

searchvalue：必需。要查找的项

startIndex：可选。起点位置的索引

### 返回值

number，查找的项在数组中的位置，没有找到的情况下返回-1

### 说明

在比较第一个参数与数组中的每一项，会使用全等操作符，即要求查找的项必须严格相等