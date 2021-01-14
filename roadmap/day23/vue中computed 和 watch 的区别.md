# computed 和 watch 的区别

computed是计算属性，watch是侦听。

**computed**

computed的作用是计算一个值，当模板中的值并不是一个简单的声明的时候，我们就可以使用computed来计算出我们要的值，然后可以直接在模板中调用这个值，并不需要加括号，并且计算属性基于依赖会自动缓存。

**watch**

我们可以使用watch来侦听和响应数据的变动并执行回调函数。vue在watch中提供了两个选项，immediate和deep，其中immediate将会使回调函数在侦听开始之前就调用一次，而deep会侦听对象中所有的数值，即使这个数值被嵌套了，也一样会监听。



一般来说，当我们想让一个数据依赖另一个数据，我们就使用computed，如果想让数据在变化的时候做事情，我们使用watch