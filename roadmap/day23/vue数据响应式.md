# vue数据响应式

所谓的数据响应式就是当你在修改vue中data的时候，vue能够检测到你的操作，并且自动更新视图。

在vue2中，vue是通过`Object.defineProperty()`给对象添加`getter/setter`来监听对于属性的读写。并且创建出的vue实例作为代理，它能够监听data的数据变化，我们也可以用它来修改数据。

