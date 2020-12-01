# JavaScript概览

> 参考阅读：
>
> [wiki百科](https://zh.wikipedia.org/wiki/JavaScript#%E5%8E%86%E5%8F%B2)
>
> [JavaScript诞生记](http://www.ruanyifeng.com/blog/2011/06/birth_of_javascript.html)
>
> [JavaScript设计的十个缺陷](http://www.ruanyifeng.com/blog/2011/06/10_design_defects_in_javascript.html)

## JS概述

一般来说，完整的JavaScript包括以下几个部分：

- ECMAScript，描述了该语言的语法和基本对象
- 文档对象模型（[DOM](https://zh.wikipedia.org/wiki/DOM)），描述处理**网页内容**的方法和接口
- 浏览器对象模型（[BOM](https://zh.wikipedia.org/wiki/浏览器对象模型)），描述与**浏览器**进行交互的方法和接口

JavaScript的基本特点如下：

- 是一种解释性脚本语言（代码不进行预编译）。
- 主要用来向HTML页面添加**交互行为**。
- 可以直接嵌入HTML页面，但写成单独的js文件有利于结构和行为的分离。

JavaScript常用来完成以下任务：

- 嵌入动态文本于HTML页面
- 对浏览器事件作出响应
- 读写HTML元素
- 在数据被提交到服务器之前验证数据
- 检测访客的浏览器信息
- 控制[cookie](https://zh.wikipedia.org/wiki/Cookie)，包括创建和修改等

## JS的历史

* 网景公司招募了[布兰登·艾克](https://zh.wikipedia.org/wiki/布蘭登·艾克)，让他做一门搭配Java使用的脚本语言，这位大佬用了十天就将JavaScript的原型设计出来了

  最初命名为Mocha，后来改成LiveScript，最后为了蹭Java的热度改成了JavaScript

* 微软看见了JavaScript的成功，所以自己推出了一款名为JScirpt来与JavaScript竞争。这两个语言的竞争也导致了没有一个统一的标准存在。

* 1996年11月，网景正式向[ECMA](https://zh.wikipedia.org/wiki/Ecma国际)（欧洲计算机制造商协会）提交语言标准。1997年6月，ECMA以JavaScript语言为基础制定了[ECMAScript](https://zh.wikipedia.org/wiki/ECMAScript)标准规范ECMA-262。JavaScript成为了ECMAScript最著名的实现之一[[19\]](https://zh.wikipedia.org/wiki/JavaScript#cite_note-:2-19)。



## ECMAScript的历史

1997年，第一版ECMAScript发布

1999年，第三版发布，这个版本使用最广

第四版流产了

2009年，第五版发布（ES5）增加了一些功能

2015年，第六版发布（ES6），新版浏览器都支持这一版

之后每年发布一版，版本号以年份命名

## JS与ECMA的标准

* ECMAScript是纸上的标准，JS是浏览器的实现
* 纸上的标准往往落后于浏览器，先实现，再写标准

## JS的爆发

* V8引擎
* 基于V8的Node.js
* 基于Node.js写出的npm
* Express.js

## 一句话

所谓专家就是把该领域内所有错误都犯完的人

