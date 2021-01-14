# MVC的理解

## 什么是MVC

MVC（Model-View-Controller）是软件工程中的一种架构模式。



MVC分为三个模块：

**Model**

​	数据模型，存取数据

**View**

​	UI界面，显示数据

**Controller**

​	控制器，在view和model中间，操作/接收view和model



我自己理解的MVC架构的逻辑是这样的，用户通过操作view层上的某一个操作，激活某一个控制器（controller），控制器负责把用户需要的数据从model中拿出来，并显示到view上。

> [谈谈MVC模式——阮一峰](http://www.ruanyifeng.com/blog/2007/11/mvc.html)



## 用伪代码来理解MVC三个模块的作用

**model**

```js
// 数据模型
const model {
    // 索引
    data : {
        num : 1;
    },
   
    // 对数据进行增删改查, 也就是对数据进行操作
	set{},
    remove{},
    update{},
    get{},     
}
```

**view**

```js
const view {
    // 初始化界面
    init() {},
    // 更新界面
    render(){},
}
```

**controller**

```js
const controller {
	
    // 事件监听器, 监听view层的事件
    eventListener() {},
	
   // 事件触发函数， 响应的事件，调用响应的函数
   events : {};
}
```

## 表驱动编程

> 表驱动法就是一种编程模式(scheme)——从表里面查找信息而不使用逻辑语句(if 和case)。事实上，凡是能通过逻辑语句来选择的事物，都可以通过查表来选择。对简单的情况而言，使用逻辑语句更为容易和直白。但随着逻辑链的越来越复杂，查表法也就愈发显得更具吸引力。



表驱动法是将把数据/信息存入表（数组/哈希表）中，然后通过表来获取我们需要的结果。



> 拓展阅读
>
> [关于if-else的重构——知乎](https://www.zhihu.com/question/37943171/answer/119525120)
>
> [表驱动法（更优雅的写if-else、switch-case）](https://juejin.cn/post/6844903996872720392)



## 关于模块化的理解

模块化将项目中的每一个功能分成了一个一个的模块，每一个模块之间都有一个对应的功能。



模块化的优点：

* 每一个模块之间相对独立，互相不会影响，方便重构
* 最小知识原则，封装好，易于使用
* 出现问题能快速定位bug
* 降低代码耦合度

