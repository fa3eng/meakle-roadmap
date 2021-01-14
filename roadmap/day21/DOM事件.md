# DOM 事件相关

## 什么是事件委托？

事件委托利用了事件冒泡原理，我们可以监听外层节点的点击事件，那么此时，当我们点击内层的节点，所有的点击事件都会冒泡到我们监听的外层节点上，然后委托外层节点代为执行事件。

> 我们可以通过target和currentTarget来区分目标元素和当前监听的元素

关于事件委托的例子：

```html
<body>
    <div id="outter">
        <div id="inner">芜湖</div>
    </div>    
</body>
```

```js
const outter = document.querySelector('#outter');
const inner = document.querySelector('#inner');

outter.addEventListener.call(outter, 'click', (event) => {
    
    // const targetName = event.target.nodeName.toLowerCase(); 得到目标元素的标签名
    if(event.target === inner){
        console.log('成功');
    }
})
```



## 怎么阻止默认动作？

两种方法：

* 使用`event` 对象里面的`event.preventDefault()`方法
* 如果是使用的`on<event>`而不是`addEventListener` ，那么可以`return false`



## 怎么阻止事件冒泡？

使用`event`对象里面的`event.stopPropagation()`。





