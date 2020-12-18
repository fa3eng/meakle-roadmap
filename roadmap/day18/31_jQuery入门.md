# jQuery入门

## jQuery 如何获取元素

jQuery通过选择表达式来获取网页上的元素。

表达式分为两种：

一种是形式为CSS选择器的选择器

```js
$(document);
$('.className');
$('#idName');
$('div.myClass'); 		// 选择类名为myClass的div
```

另一种形式为JQuery独有的形式：

```js
$('a: first');			// 选择网页中第一个a标签
$('tr: odd');			// 选择表格中的奇书行
$('#Myform: input'); 	// 选择ID为Myform中的input标签
```

> `'xxx:bbb'`选择xxx中的bbb。xxx是范围，bbb是条件

## jQuery 的链式操作是怎样的

链式操作其实就是，我调用了某一个函数或者方法，这个函数或者方法所返回的值是一个对象，所以我们就可以继续调用这个对象中的方法来得到我们想要的结果。

```js
let obj = $('div');					// 返回一个对象，代表着页面中的所有div元素
let obj2 = obj.find('h1');			// 找到h1这个元素，返回一个对象，包含着所有在div中的h1元素
obj2.html('hello');					// 将所有的h1元素的内容改为hello

// 这个上面是普通的调用方式，下面我们使用链式操作
$('div').find('h1').html('hello');	// 这个和上面三行的内容是一样的。
```

## jQuery 如何创建元素

```js
let obj = $('<p>test</p>');								// 创建一个元素p，其文本节点为test, 返回这个jQuery对象
let obj2 = $('<li class="new">new list item</li>'); 	// 创建一个li元素，class值为new，返回这个Query对象

$('body').[obj];										// 把obj对象append到body节点上
```

## jQuery 如何移动元素

```js
$('div').insertAfter($('p'));			// 将文档中所有的div放在p标签后面，返回$('div')
$('p').after($('div'));					// 将文档中的所有p标签放在div标签前面，返回$('p')
```

这两个所实现的效果是一样的。

但是所返回的jQuery对象是不一样的。

```js
.insertAfter()和.after()：在现存元素的外部，从后面插入元素

.insertBefore()和.before()：在现存元素的外部，从前面插入元素

.appendTo()和.append()：在现存元素的内部，从后面插入元素

.prependTo()和.prepend()：在现存元素的内部，从前面插入元素
```

## jQuery 如何修改元素的属性

jQuery的设计思想是：使用一个函数，来完成取值（getter）和赋值（setter）。

取值或者是赋值取决于函数的参数。（重载）

```js
$('p').html();				// 获取p标签里面的值
$('p').html('wuhu~');		// 设置p标签里面的值为wuhu~
```

常见的取值赋值函数如下：

```js
.html() 取出或设置html内容

.text() 取出或设置text内容

.attr() 取出或设置某个属性的值

.width() 取出或设置某个元素的宽度

.height() 取出或设置某个元素的高度

.val() 取出某个表单元素的值
```









