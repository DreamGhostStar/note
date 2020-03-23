---
title: JavaScript基础知识点--event对象常用属性和方法
date: 2019-09-01 15:11:45
tags: JavaScript
categories: JavaScript
---
---

# event常用属性和方法

## 常用属性和方法表

属性或方法|说明
-|-
type|事件的类型
srcElement/target|事件源，就是发生事件的元素
cancelBubble|布尔属性。设为 true 的时候，将停止事件进一步起泡到包容层次的元素（Ele.cancelBubble = true;相当于Ele.stopPropagation();）
returnValue|布尔属性。设置为 false 的时候可以阻止浏览器执行默认的事件动作（Ele.returnValue = false;相当于Ele.preventDefault();）
clientX/clientY|事件发生的时候，鼠标相对于浏览器窗口可视文档区域的左上角的位置
offsetX/offsetY|事件发生的时候，鼠标相对于事件源元素左上角的位置
initEvent()|初始化新创建的Event对象的属性

说明：event 对象的所有属性列表可以在浏览器控制台中输出查看

## event.type

返回当前触发事件的类型

## event.target

事件源。返回触发事件的元素

## event.currentTarget

返回事件绑定的元素

## event.preventDefault()

阻止浏览器执行默认行为

## event.stopPropagation()

阻止事件的捕获或冒泡

## event.clientY

clientY 事件属性返回当事件被触发时鼠标指针距浏览器顶部底边的距离，不包括滚动条滚动的部分

## event.pageY

pageY 事件属性返回当事件被触发时鼠标指针距浏览器顶部底边的距离，包括滚动条滚动的部分

## event.screenY

屏幕顶端到鼠标位置

## event.button

值|代表
-|-
0|鼠标左键
1|鼠标中键
2|鼠标右键

## touchcancel

当系统停止跟踪触摸时触发

## event.touches

当前触摸屏幕的触摸点数组

## event.changedTouches

数组中只包含引起事件的触摸点信息

## event.targetTouches

只包含放在元素上的触摸信息

## IE事件独有

### event.returnValue = false

阻止默认行为。同 preventDefault

### event.cancleBubble = true

取消事件冒泡。同 stopPropagation

### srcElement

同 target

### event.button

值|代表
-|-
0|没有按下按钮
1|按下主鼠标按钮
2|按下次鼠标按钮
3|同时按下主、次鼠标按钮
4|按钮中间鼠标按钮

