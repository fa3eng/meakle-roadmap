# vue入门

> 笔记，新手入门，可能错误百出。

## 引入

要引入vue非常容易，我们可以直接用标签来引入。

```html
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
```

## hello world

1. 首先创建出一个html界面
2. 然后用`script`标签引入vue

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
</body>
</html>
```

### 声明式渲染

> Vue.js 的核心是一个允许采用简洁的模板语法来声明式地将数据渲染进 DOM 的系统



我们在`body`中声明一个入口

```html
<div id="app">
        {{message}}
</div>
```

现在我们可以开始写vue了

```js
// 新建的vue对象
new Vue ({
    // 挂载点，也就是说我要把这个vue实例挂到dom中id是app的地方
    el: '#app',
    // 数据
    data(){
        return{
            message : 'hello world',
        };
    }
})
```

完成。



### 响应式

页面上的内容并不是一成不变的，他会响应式的更改

我们可以给某一个元素绑定一个会变化的信息值来看这个问题。

```html
<div id="app2">
        <span v-bind:title="message">悬浮在上面</span>
</div>
```

```js
new Vue ({
    el: '#app2',
    data(){
        return {
            message : `我来告诉你现在的时间是${new Date().toLocaleString()}`
        };
    }
})
```



* 在`span`标签中，出现了一个属性叫`v-bind`，这是vue提供给我们的属性，他的作用是绑定`span`标签的`title`值为message。



## 条件与循环

vue不仅仅可以将数据绑定在文本（hello world）和attribute（响应式的例子）上，还可以绑定DOM结构。



### 条件

我们可以给某一个元素添加`v-if = "xxx"`这个属性，vue通过判断xxx的布尔值来决定这个元素是否被渲染

```html
<div id="app">
    <button @click = "hidden">消失或出现</button>
    <div v-if = 'hide'>我点一下按钮就消失</div>
</div>
```

```js
new Vue({
    el: '#app',
    data(){
        return {
            hide : true
        };
    },
    methods:{
        hidden(){
            this.hide = !this.hide;
        }
    }
})    
```



梳理一下：

我们给`div` 标签添加了`v-if`，然后我们在vue实例中令它的初始值为true。因此在页面刚初始化的时候，`我点一下按钮就消失`这行字是存在于页面当中的。

我们在页面中又创建了`button`标签，并给他一个点击事件，让`button`被点击的时候执行名为`hidden`的回调函数，然后我们再把目光转向vue实例，我们整了一个新对象叫`methods`，然后我在里面写了一个函数名为`hidden`，它的作用是将`hide`的值变为其取反之后的值。



### 循环

```html
<div id="app">
        <ol>
            <li v-for = "todo in todoList">
                {{todo.text}}
            </li>
        </ol>
</div>
```

```js
new Vue({
    el: '#app',
    data(){
        return {
            todoList: [
                {text: '好好学习'},
                {text: '学好框架'},
                {text: '弄个项目'}
            ]          
        };
    },  
})
```

梳理一下：

在`li`标签中给了一个`v-for`的属性，里面的值是`todo in todoList`。todo是循环的item，而todoList是数组，换句话说数组todoList中有几个值，就会循环几次，相对应的`li`就会被创建几次，而模板`{{todo.text}}`要获取的就是数组中元素的text值。剩下data里面的值就是呼应了上面。



















