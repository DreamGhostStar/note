---
title: JavaScript进阶知识点--JS面向对象
date: 2019-09-15 14:41:21
tags: JavaScript
categories: JavaScript
---
---

# 面向对象

对代码的一种抽象，对外同一提供调用接口的编程思想

## 基于原型的面向对象

基于原型的面向对象方式中，对象（object）则是依靠构造器（constructor）利用原型（prototype）构造出来的

## JS面向对象的名词解释

+ 属性：事物的特效

+ 方法：事物的功能

+ 对象：事物的一个实例

+ 原型：JS函数中由 prototype 属性引用了一个对象，即原型对象（原型）

## JS中的闭包

闭包是一个拥有许多变量和绑定了这些变量的环境的表达式（通常是一个函数）

### 用途

1. 读取函数内部变量

2. 让在函数内部声明的变量的值保留在内存中

### 闭包的优缺点

#### 优点

1. 有利于封装

2. 可以访问局部变量

#### 缺点

1. 内存占用浪费严重

2. 内存泄漏

### 分析闭包

1. 函数嵌套函数，这是闭包的一个结构。

2. 函数里的子函数被函数外部一直使用，使子函数无法释放，保持其所在作用域，形成一个封闭的作用域，称之为闭包。

## 对象

### 创建对象

1. 字面量（P83）

2. new 操作符后跟 Object 构造函数（P83）

3. JS中构造函数方法声明对象

    ```
        function test([参数列表]){
            this.属性 = 属性值;
            this.方法 = function () {
                方法中代码
            }
        }

        var obj = new test(参数列表);
    ```

# JS 设计模式

任何模式下，同种模式中的创造出来的对象都是独立存在的

## 工厂模式

```
    function createObject(name, age) {
        var obj = new Object();
        obj.name = name;
        obj.age = age;
        obj.run = function() {
            return this.name + this.age + '运行中...';
        };
        return obj;
    }

    var box1 = createObject('zhangsan', 100);
    var box2 = createObject('lisi', 200);
```

## 构造方式

1. 构造方式不会显示创建对象，将属性赋值给 this ，不需要 return 对象

2. 工厂模式在方法内部创建 object 对象，返回 object 对象，属性和方法都是赋给 object 对象

## 原型模式

```
    function test() {
    }
    test.prototype.属性 = 属性值;
    test.prototype.属性 = 属性值;
    test.prototype.方法名称 = function() {
        执行代码;
    }

    var obj = new test();
```

### 原型模式的写法原理

函数本身声明为空内容，利用 prototype 定义一些属性及方法

### 好处

让所有实例化的对象都拥有它包含的属性及方法

## 混合模式

```
    function test(v1, v2, v3) {
        this.v1 = v1;
        this.v2 = v2;
        tihs.v3 = v3;
    }

    test.prototype.方法名称 = function() {
        执行代码
    }

    var obj = new test(v1, v2, v3);
```

# 遍历

```
    var ren = {};
    ren.name = "zhangsan";
    ren.age = 18;
    ren.demo = function() {
        document.write("aaaa");
    }

    for(var i in ren){
        // alert(i);    //弹出属性和方法名称
        alert(ren[i]);
    }

    // i是所有的属性或方法名称
```

# 封装

封装（Encapsulation）：把对象内部数据和操作细节进行隐藏

大多数面向对象的语言都支持封装的特性，提供了 private 关键字来隐藏某些属性或方法，用来限制被封装的数据或者内容的访问，只对外提供了一个对象的专门访问的接口

接口一般为调用方法

JavaScript中可以通过闭包实现封装

# 原型和原型链

## 原型

是利用 prototype 添加属性和方法

## 原型链

JS在创建对象（不论是普通对象还是函数对象）的时候，都有一个叫做_proto_的内置属性，用于指向创建它的函数对象的原型对象 prototype

# 对象冒充

将父类的属性和方法一起传给子类作为特权属性和特权方法

原型属性和原型方法不属于特权属性和特权方法