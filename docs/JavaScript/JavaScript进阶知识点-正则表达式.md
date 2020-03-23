---
title: JavaScript进阶知识点--正则表达式
date: 2019-09-19 19:47:51
tags: JavaScript
categories: JavaScript
---
---

# 正则表达式

## 什么是正则表达式

由以下两种字符组成的文字模式

1. 普通字符（例如26个英文字母、数字、汉字、`_`、`,`，不含有特殊含义的符号等）

2. 特殊字符（有特殊含义的，例如`.\`等）

该模式描述在查找文字主体时待匹配的一个或多个字符串。正则表达式作为一个模板，将某个字符模式与说搜索的字符串进行匹配

正则表达式匹配的一定是字符串中的内容

## 方法

### test

如果找到，则返回 true

如果未找到，则返回 false

```
    var str = "I love js";
    var pattern = /js/;

    console.log(pattern.test(str));
```

### exec

如果找到，则将在字符串中找到的该字符传入一个数组中，并将该数组返回

如果未找到，则返回 null

## flags

flags|作用
-|-
g|表示全局(global)模式，即模式将被应用于所有字符串，而非在发现第一个匹配项时立即停止
i|表示不区分(case-insensitive)模式，即在确定匹配项时忽略模式与字符串的大小写
m|表示多行模式，即在到达一行文本末尾时还会继续查找下一行中是否存在于模式匹配的项

# 转义字符

+ 如果使用字面量的方式定义正则，一个反斜杠转义

+ 如果使用构造函数方式定义正则，需要用到双重反斜杠

有问请查看文件中的`特殊字符总结`，`常用正则表达式总结`

常用的字符类|意义
-|-
`/./`|表示除了换行符之外的所有字符
`/\w/`|等同于`/[a-zA-Z0-9_]/`
`/\W/`|等同于`/[^a-zA-Z0-9_]/`
`/\d/`|等同于`/[0-9]/`
`/\D/`|等同于`/[^0-9]/`
`/\s/`|匹配空格和制表符之类的
`/\S/`|匹配空格和制表符之类的空白字符以外的所有字符
`/\b/`|单词的边界匹配

中文的 Unicode 编码为`\u4e00-\u9fa5`

# 重复

以下均为贪婪匹配

代码示例

```
    <!-- 匹配n个字符 -->
    var str = "110";
    var pattern = /\d{3}/; // {}中表示匹配的个数
    console.log(pattern.exec(str)); // ["110"]

    <!-- 匹配至少n个字符 -->
    var str = "110";
    var pattern = /\d{1,}/; // 至少1个
    console.log(pattern.exec(str)); // ["110"]

    <!-- 匹配n个到m个 -->
    var str = "110";
    var pattern = /\d{0,1}/; 
    console.log(pattern.exec(str)); // ["1"]

    <!-- 匹配0个或者1个 -->
    var str = "110";
    var pattern = /\d?/; 
    console.log(pattern.exec(str)); // ["1"]

    <!-- 至少匹配1个 -->
    var str = "110";
    var pattern = /\d+/; 
    console.log(pattern.exec(str)); // ["110"]

    <!-- 至少匹配0个 -->
    var str = "110";
    var pattern = /\d*/; 
    console.log(pattern.exec(str)); // ["110"]
```

## 非贪婪匹配

在量词后面加`?`

```
    <!-- 至少匹配1个 -->
    var str = "110";
    var pattern = /\d+?/; 
    console.log(pattern.exec(str)); // ["1"]
```

# 选择、分组、引用

## 选择

代码示例

```
    var str = "html js";
    var pattern = /html|css|js/; 
    console.log(pattern.exec(str)); // ["html"]
```

## 分组

```
    var str = "ababab";
    var pattern = /(ab)+/; 
    console.log(pattern.exec(str)); // ["ababab", "ab"]

    <!-- 非捕获性分组 -->
    var str = "ababab";
    var pattern = /(?:ab)+/; 
    console.log(pattern.exec(str)); // ["ababab"]
```

## 引用

```
    <!-- 捕获性分组的引用 -->
    var str = "ab cd ab";
    var pattern = /(ab) cd \1/; 
    console.log(pattern.exec(str)); // ["ab cd ab", "ab"]
```

# 首尾匹配

```
    <!-- 首匹配 -->
    var str1 = "js";
    var str2 = "html js";
    var pattern = /^js/;
    console.log(pattern.exec(str1)); // ["js"]
    console.log(pattern.exec(str2)); // null

    <!-- 尾匹配 -->
    var str1 = "js";
    var str2 = "js html";
    var pattern = /js$/;
    console.log(pattern.exec(str1)); // ["js"]
    console.log(pattern.exec(str2)); // null
```

# 前瞻性匹配

```
    <!-- 在这个例子中，只有java后面跟了script才会匹配成功 -->
    var str = 'javascript';
    var pattern = /java(?=script)/;
    console.log(pattern.exec(str)); // ["java"]
```

# 负向前瞻性匹配

```
    <!-- 在这个例子中，如果java后面跟了script则不会匹配java -->
    var str = 'javascript';
    var pattern = /java(?!script)/;
    console.log(pattern.exec(str)); // null
```

# RegExp 的实例

## 方法

方法|作用
-|-
test(str)|返回布尔值。判断该字符串是否有该匹配式
exec(str)|返回数组。找到该匹配式，将匹配成功的字符放入数组中
toString()|返回字符串。将匹配式转换为字面量的字符串
toLocaleString()|返回本地字符。其实没多大区别
valueOf()|返回该匹配式的字符串形式

## 属性

属性|作用
-|-
ignoreCase|判断 flags 是否有i
global|判断 flags 是否有g
multiline|判断flags是否有m
source|返回字面量形式的字符串
lastIndex|返回数值。每次检索完毕的最终位置

## 构造函数属性

构造函数属性|作用
-|-
RegExp.input|返回检索的字符串
RegExp.$_|和 RegExp.input 作用相同
RegExp.lastMatch|返回最近一次匹配的字符
RegExp['$&']|和 RegExp.lastMatch 作用相同
RegExp.leftContext|上一次匹配左边剩余的字符
RegExp.rightContext|上一次匹配右边边剩余的字符
RegExp.lastParen|上一次捕获的分组的字符
RegExp.$1|第一个分组的引用，与`\1`作用相同

# String对象中与正则表达式相关的方法

## search

返回一个 Number ，找到匹配的字符的位置

```
    var str = "html js";
    var pattern = /js/;
    console.log(str.search(pattern)); // 5
```

## match

和exec一样，返回的是一个类数组的对象

### 区别

```
    var str = "js js js";
    var pattern = /js/g;
    console.log(str.match(pattern)); // ["js", "js", "js"]
```

`match`： 非全局的情况下才会返回分组中匹配到的内容，全局匹配只能匹配到所有匹配到的字符

`exec`：无论是否全局匹配都会返回分组中匹配到的内容，都只会返回当前匹配到的一个内容，而不是全部返回

## replace

```
    <!-- 全部替换 -->
    var str = "I love js js";
    var pattern = /js/g;
    console.log(str.replace(pattern, "html"));
```