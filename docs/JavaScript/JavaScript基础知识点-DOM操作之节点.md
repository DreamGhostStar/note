---
title: JavaScript基础知识点--DOM操作之节点
date: 2019-08-26 20:55:06
tags: JavaScript
categories: JavaScript
---
---

# DOM之节点

+ 添加节点

+ 删除节点

+ 修改节点

+ 查找节点

# 添加节点

## create 系列方法

+ document.creatElement()：创建新的元素节点。一个参数，标签名

+ document.createTextNode()：创建新的文本节点。一个参数，要插入的节点的文本

+ document.createDocumentFragment()：创建文档片段

+ document.createComment()：传入一个注释文本，创建一个注释节点

+ node1.appendChild(node2);将node2（节点二）装填到node1（节点1）内。

document.createElement 还能支持创建当前浏览器不支持的标签名，在IE6-8下，这是一个著名的 hack

### 创建节点示例一

```
    var newDiv = document.createElement("div"); // 创建元素节点，这句话就是在窗口创建div元素
    var newContent = document.createTextNode("Hi there and greetings!"); // 创建文本节点及其内容
    newDiv.appendChild(newContent); // 将文本节点装填到元素节点内
```

### 创建节点示例二

```
var comment = document.createComment("A comment");
    var fragment = document.createDocumentFragment();
    var ul = document.getElementById("myList");// HTML 文档中ul的id为myList
    var li = null;
    for(var i = 0; i < 3; i++){
        li = document.createElement("li");
        li.appendChild(document.createTextNode("Item "+ (i+1)));
        fragment.appendChild(li);
    }
    ul.appendChild(fragment);
    // insertBefore 有两个参数，一个是要插入的节点，另一个是插入节点相对的对象，插入节点要插入到哪个对象的前面的对象，这里的第二个参数是ul
    document.body.insertBefore(comment, document.body.firstChild);
```

# IE 浏览器条件编译

```
    // 如果是IE浏览器，则!!0为假，不return。如果不是IE浏览器，则!0为真，返回并且不执行条件编译后面的代码
    if(!
    /*@cc_on!@/
    0) return;
```

# 高效创建节点的方法

+ innerHTML：用来设置或获取当前标签的起始和结束里面的内容

+ outerHTML：返回调用它的元素及所有子节点的 HTML 标签，包含元素自身的标签

+ innerText：设置或获取位于对象起始和结束标签内的文本，低版本火狐浏览器不支持，可用 textContent 方法

## 使用 innerHTML 的限制

+ 字符串的最左边不能出现空白，IE6~8会自动移除它

+ 大多数浏览器不会对 script 标签进行脚本执行操作

    1. 为 script 标签添加 defer 属性

    2. script 标签要在有作用域的元素之后

+ 不能单独创建 meta，style，link等元素，一定要在前面加上一些字符

## 避开空白节点

1. nodeType

2. 第二套 API

# 类数组对象

## NodeList 对象的特点

NodeList 是 childNodes 的保存的对象

+ NodeList 是一种类数组对象，用于保存一组有序的节点

+ 可以通过方括号语法来访问 NodeList 的值，有 item 方法与 length 属性

+ 它并不是 Array 的实例，没有数组对象的方法

## 类数组对象 HTMLCollection

+ Ele.getElementsByTagName()：会根据节点的名称返回一组元素的集合

+ document.scripts：会返回页面里的全部 script 的集合

+ document.links：会返回页面里的全部 a 元素

+ document.images：会返回页面里的全部 image 元素

+ document.forms：会返回页面里全部的页面表单

+ tr.cells：会返回 tr 的所有 td 子元素的集合

+ select.options：会返回这个 select 属性的全部选项

## namedItem() 

该方法返回 HTMLCollection 对象中指定 ID 或 name 的元素

### 语法

> HTMLCollection.namedItem(name)

### 参数说明

name：必需。你要返回元素的 id 或 name 属性的值

## 类数组对象 NamedNodeMap

主要用于获取属性的属性值

+ Ele.attributes：返回指定节点的属性集合

+ Ele.attributes.getNamedItem(“attributeName”).nodeValue：返回指定的属性节点。attributeName为要查找的属性值的属性名，该方法只能获取在元素上定义的属性值

## 类数组对象的动态性

+ NodeList，HTMLCollection，NamedNodeMap 三个集合都是动态的，是有生命的、有呼吸的对象

+ 它们实际上是基于 DOM 结构动态执行查询的结果，因此 DOM 结构的变化能够自动反映这些对象

+ 每当文档结构发生变化时，它们都会得到更新。因此，它们始终都会保存着最新、最准确的信息

# 节点查找方法

+ getElementById()

+ getElementsByName()

+ getElementsTagName()

+ getElementsByClassName()

+ querySelector()：返回文档中匹配指定 CSS 选择器的一个元素，括号中写符合 CSS 语法的字符

+ querySeletorAll()：返回文档中匹配指定 CSS 选择器的一组元素，括号中写符合 CSS 语法的字符

前三个只能是 document 对象的方法

querySelectorAll() 和 querySelector() 方法返回的是一个静态的 NodeList ,所谓静态 NodeList 就是对底层 document 的更改不会影响到返回的这个 NodeList 对象.此时返回的 NodeList 只是 querySelectorAll() 方法被调用时的文档状态的快照。

# 操作节点

+ appendChild()：为指定元素节点的最后一个子节点之后添加节点。该方法返回新的子节点

+ insertBefore()：在指定的已有子节点之前插入新的子节点。该方法返回新创建的节点

+ replaceChild()：新节点替换某个子节点。返回被替换的节点

+ cloneNode()：创建节点的拷贝，并返回该副本。拷贝的节点要有父节点，如果没有父节点，要通过上面三个方法对其进行添加

+ normalize()：合并相邻的文本节点

+ splitText()：按照指定的位置把文本节点分割为两个节点。返回分割后新的文本节点

## 参数说明

方法|参数
-|-
appendChild()|appendChild(要插入的节点)
insertBefore()|insertBefore(要插入的节点，指定的子节点)
replaceChild()|replaceChild(要插入的节点，被替换的节点)
cloneNode()|cloneNode(boolean)，若Boolean为false，则只复制该节点。如果未true，则为深度拷贝，将该节点下的子节点一起拷贝
splitText()|splitText(num)，节点从num位置被分割，包括num该位置的字符

## nodeValue 与 innerHTML 的区别

### nodeValue

nodeValue 属性设置或返回指定节点的节点值。（文本节点和属性节点可以用nodeValue）

### innerHTML

innerText属性可以获取或者设置指定元素的文本内容

### 区别

nodeValue 只会读取 element 这个节点的节点值，不包括子节点，而 innerHTML 包括子节点

# 删除节点

## 涉及方法

+ removeChild()：删除某个节点中指定的子节点。返回被删除的节点

+ removeNode()：IE的私有实现。将目标节点从文档中删除，返回目标节点

+ innerHTML

+ deleteContents

+ textContent

## 参数说明

方法|参数说明
-|-
removeChild()|一个参数。为要删除的子节点
removeNode()|一个参数为布尔值，默认值为false。若为false，仅删除目标节点，保留子节点。若为true，功能和removeChild类似
