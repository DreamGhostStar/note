---
title: JavaScript基础知识点--DOM属性
date: 2019-08-31 09:34:26
tags: JavaScript
categories: JavaScript
---
---

# 认识属性

HTML 属性分为两种

1. property：固有属性

2. attribute：自定义属性

## 属性说明

+ Ele.attributes：返回指定节点的属性集合

+ Ele.attributes.getNamedItem(“attributeName”).nodeValue：返回指定的属性节点。attributeName为要查找的属性值的属性名，该方法只能获取在元素上定义的属性值

+ Ele.attributes.removeNamedItem("attributeName")：移除指定的属性节点

+ Ele.attributes.setNamedItem("attribute")：将已有的属性节点设置给该元素

+ document.createAttribute("arributeName")：在文档中创建一个属性节点。若是要为指定元素添加属性，需要到 setNamedItem() 方法或 setAttributeNode() 方法

+ nodeName：会根据所属节点类型返回节点的名称

    nodeName所属节点的类型|返回值
    -|-
    元素节点|标签名称
    属性节点|属性名称
    文本节点|#text
    文档节点(document)|#document

+ nodeValue：会根据所属节点类型返回节点的值。nodeValue 属性对于文档节点和元素节点是不可用的

    nodeValue所属节点的类型|返回值
    -|-
    文本节点|文本
    属性节点|属性值

+ nodeType：返回一个数值代表节点的类型

    接口|nodeType常量|nodeType值|备注
    -|-|-|-
    Element|Node.ELEMENT_NODE|1|元素节点
    Text|Node.TEXT_NODE|3|文本节点
    Document|Node.DOCUMENT_NODE|9|document
    Comment|Node.COMMENT_NODE|8|注释的文本
    DocumentFragment|Node.DOCUMENT_FRAGMENT_NODE|11|文档片段
    Attr|Node.ATTRIBUTE_NODE|2|节点属性

+ Ele.getAttribute("attributeName")：获取该属性名的属性值。包括固有属性和自定义属性

+ Ele.setAttribute(attributeName, attributeValue)：添加或修改元素的属性节点的属性值

+ Ele.removeAttribute(attributeName)：移除该元素指定的属性名及其属性值

+ Ele.setAttributeNode(attribute)：将属性节点添加到指定元素内

# nodeValue 与 value 的区别

nodeValue 属性根据节点的类型设置或返回节点的值。这里创建了一个属性节点，然后给这个节点添加了值

value 属性用于设置或者返回属性的值。这里是直接属性添加值

# 为元素添加属性

## 第一种方法

```
    Ele.color.colorName="colorValue";
```

## 第二种方法

```
    Ele.setArribute("arributeName", "arributeValue");
```

## 第三种方法

```
    var arr=document.createAttribute("arributeName");// 设置元素节点的属性名
    arr.value="arributeValue";// 设置元素节点的属性值
    Ele.setAttributeNode(arr);// 将元素节点添加到元素中
```

## 第四种方法

```
    var data = document.createAttribute("data");
    data.value = "wrap";
    div.attributes.setNamedItem(data);// 为元素添加指定节点
```

# 移除属性节点

```
    Ele.attributes.removeNamedItem("attributeName");
```

# 其他属性

## HTML 标签的布尔属性

如 disabled、multiple、readonly、checked、selected 等属性

## 字符串属性

如 id、title（鼠标滑过时的提示信息）、href、src、lang、dir（文本的输出方向）、accesskey（通过快捷键使某个元素快捷选中，快捷键为Alt+定义的键）、name、value、class 等属性

### W3C全局属性

accesskey、class、contenteditable（是否可编辑的内容）、dir、hidden、id、lang、spellcheck、style、tabindex（规定当使用“tab”键进行导航时元素的顺序）、title、translate（规定是否应该翻译元素内容，目前所有主流浏览器都无法正确支持该属性）

# classList

+ add(classValue)：为元素添加class类名

+ remove(classValue)：为元素移除class类名

+ contain(classValue)：判断该元素是否存在某个class

+ toggle(classValue)：如果有该classValue，则删除。若没有，则添加上