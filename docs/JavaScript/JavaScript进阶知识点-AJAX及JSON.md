---
title: JavaScript进阶知识点--AJAX及JSON
date: 2019-09-26 12:35:35
tags: JavaScript
categories: JavaScript
---
---

# AJAX

## 关于 AJAX

### 什么是 AJAX

AJAX 的全称是 Asynchronous JavaScript and XML（即异步的 JavaScript 和 XML，它并不是一种新的编程语言，而是几种原有技术的结合体

AJAX 是一种在无需重新加载整个网页的情况下，能够更新部分网页的技术

### 为什么要使用 AJAX？

#### AJAX 的优点

+ 通过异步模式，提升了用户体验

+ 优化了浏览器和服务器之间的传输，减少不必要的数据往返，减少了带宽占用

+ AJAX 引擎在客户端运行，承担了一部分本来由服务器承担的工作，从而减少了大用户量下的服务器负载

#### AJAX 的缺点

+ 不支持浏览器 back 按钮

+ 安全问题 AJAX 暴露了与服务器交互的细节

+ 对搜索引擎的支持比较弱

## XMLHTTPRequest 对象

### 什么是 XMLHTTPRequest？

是一种支持异步请求的技术，它是 AJAX 的核心

### XMLHTTPRequest 的作用

+ 可以先服务器提出请求并处理响应，而不阻塞用户

+ 可以在页面加载以后进行页面的局部更新

## 如何使用 AJAX？

要完整实现一个 AJAX 异步调用和局部刷新，通常需要以下几个步骤

+ 创建 XMLHTTPRequest 对象，也就是创建一个异步调用对象

+ 创建一个新的 HTTP 请求，并指定该 HTTP 请求的方法、URL

+ 设置响应 HTTP 请求状态变化的函数

+ 发送 HTTP 请求

+ 获取异步调用返回的数据

+ 使用 JavaScript 和 DOM 实现局部刷新

## 如何创建 HTTP 请求

### 语法

> open(method, url, async)

### 功能

创建 HTTP 请求，规定请求的类型、URL及是否异步处理请求

### 参数说明：

+ `method`：请求类型，GET或POST

+ `url`：文件在服务器上的位置

+ `async`：true（异步）或 false（同步）

### 注意事项：

`open` 方法不会向服务器发送真正请求，它相当于初始化请求并准备发送只能向同一个域中使用相同协议和端口的URL发送请求，否则会因为安全原因报错

#### URL

`url` 参数是 `open()` 方法中唯一一个必须要指定的参数，用来设置服务器上文件的地址，该文件可以是任何类型的文件，如.txt 和 .xml，或者服务器脚本文件，如.asp 和 .php（在传回响应之前，能够在服务器上执行任务）

#### GET 和 POST 的区别

与 `POST` 相比，`GET` 更简单也更快，并且在大部分情况下都能用，然而，在以下情况中，必须使用 POST 请求：

+ 无法使用缓存文件（更新服务器上的文件或数据库）

+ 向服务器发送大量数据（POST 没有数据量限制）

+ 发送包含未知字符的用户输入时，`POST` 比 `GET` 更稳定也更可靠

#### 同步和异步的区别

+ 同步：提交请求 -> 等待服务器处理 -> 处理完毕返回 这个期间客户端浏览器不能干任何事

+ 异步：请求通过事件触发 -> 服务器处理（这是浏览器仍然可以作其他事情）-> 处理完毕

#### async

说明：`async` 是一个布尔值。

如果是异步通信方式（true），客户机就不等待服务器的响应

如果是同步方式（false），客户机就要等到服务器返回消息后才去执行其他操作

## 设置响应 HTTP 请求状态变化的函数

请求发往服务器 -> 服务器根据请求生成响应 -> 传回给 XHR 对象

在收到响应后相应数据会填充到 XHR 对象的属性，有四个相关属性会被填充：

+ responseText：从服务器进程返回数据的字符形式

+ responseXML：从服务器进程返回的 DOM 兼容的文档数据对象

+ status：从服务器返回的数字代码，如 404（未找到）和200（已就绪）

+ statusText：伴随状态码的字符串信息

## 如何发送请求

### 语法

> send(string)

### 功能

将请求发送到服务器

### 参数说明

string 仅用于 post 请求

### 注意事项

仅在 POST 请求时可以传入参数，不需要则发送 null，在调用 send 方法之后请求被发往服务器

## 如何添加 HTTP 头

如果需要像 HTML 表单那样 POST 数据，需使用 setRequestHeader() 来添加 HTTP 头，然后在 send() 方法中规定希望发送的数据

### 语法

> xmlhttp.setRequestHeader(header, value)

### 使用

```
    xmlhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
```

# JSON

## 什么是 JSON？

JSON（JavaScript object notation）全称是 JavaScript 对象表示法，它是一种数据交换的文本格式，而不是一种编程语言，用于读取结构化数据，2001年由 Douglas Crockford 提出，目的是取代繁琐笨重的 XML 格式

## JSON 的语法规则

JSON 的语法可以表示以下三种类型的值：

### 简单值：

简单值使用与 JavaScript 相同的语法，可以在 JSON 中表示字符串、数值、布尔值和 null

字符串必须使用双引号表示，不能使用单引号，数值必须以十进制表示，且不能使用 NaN 和 Infinity

说明：JSON 不支持 JavaScript 中的特殊值 undefined

### 对象：

对象作为一种复杂数据类型，表示的是一组有序的键值对，而每个键值对中的值可以是简单值，也可以是复杂数据类型的值

JSON 中对象的键名必须放在双引号里面，因为 JSON 不是 JavaScript 语句，所以没有末尾的分号

说明：同一个对象不应该出现两个同名属性

### 数组：

数组也是一种复杂数据类型，表示一组有序的值的列表，可以通过数值索引来访问其中的值

说明：数组或对象最后一个成员的后面，不能加逗号

# JSON 对象

JSON 对象的两个方法：

## parse()

### 语法

> JSON.parse()

### 功能

用于将 JSON 字符串转换成对象

## stringify()

### 语法

> JSON.stringify()

### 功能

用于将一个值转为字符串，该字符串应该符合 JSON 格式，并且可以被 JSON.parse()方法还原

## JSON 对象总结

+ JSON 之所以流行，是因为可以把 JSON 数据结构解析为有用的 JavaScript 对象

+ JSON 对象 的 stringify()和 parse()这两个方法可以分别用于把 JavaScript 对象序列化为 JSON 字符串和把 JSON 字符串解析为原生 JavaScript 值

+ JavaScript 的 eval() 类似于 JSON.parse() 方法，可以将 json 字符串转换为 json 对象，但是，eval() 可以执行不符合 JSON 格式的代码，有可能会包含恶意代码，所以尽量少用

# jQuery 的 ajax 方法

+ `$.ajax()`

+ `$.get()`

+ `$.post()`

+ `$.getJson()`

# 跨域

## 什么是同源策略

所谓同源是指：域名，协议，端口均相同

## 什么是跨域

跨域是指从一个域名的网页去请求另一个域名的资源，严格一点的定义是：只要协议，域名，端口有任何一个的不同，就被当作跨域

## 如何解决跨域

+ 跨域资源共享（CORS）

+ JSONP（常用）

+ 修改 `document.domain`

+ 使用 `window.name`

## 如何使用 JSONP 解决跨域

### 什么是 JSONP

JSONP 是 JSON with Padding（填充式json）的简写，是应用 JSON 的一种新方法，也是一种跨域解决方案

### JSONP 的组成

JSONP 由两部分组成：回调函数和数据。回调函数是当响应到来时应该在页面中调用的函数，而数据就是传入回调函数中的 JSON 数据

### JSONP 的原理

直接用 XMLHTTPRequest 请求不同域上的数据时，是不可以的。但是，在页面上引入不同域上的 js 脚本文件却是可以的，JSONP 正是利用这个特性来实现的

通过 script 标签引入 js 文件 -> js 文件载入成功后 -> 执行我们在 url 参数中指定的函数