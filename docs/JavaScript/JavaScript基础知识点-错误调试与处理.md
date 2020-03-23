---
title: JavaScript基础知识点--错误调试与处理
date: 2019-08-24 16:14:51
tags: JavaScript
categories: JavaScript
---
---

## 断点

> debugger

在浏览器运行到这段代码时，触发断点

## try catch语句

```
try{
    //如果内部的代码抛出错误，则代码直接跳入 catch 块运行，且把错误对象赋值给 catch 括号内的变量
} catch(e){
    //如果出现错误，则执行这块代码
} finally{
    //做一些清理性的工作
    //finally 块是一定会执行的
}
```

### 抛出错误

> throw new Error(错误语句)

如果抛出错误不在 try 语句中，那么它会寻找最近的 try catch 语句