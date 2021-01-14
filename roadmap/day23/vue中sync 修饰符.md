# .sync 修饰符的作用

vue 修饰符sync的功能是：当一个子组件改变了一个 prop 的值时，这个变化也会同步到父组件中所绑定。

`.sync` 修饰符是一个语法糖，它会被扩展为一个自动更新父组件属性的 v-on 监听器。



我们来举例说明：

我们现在有一个父组件，他有一个值为1000，子组件获取这个值，并且子组件中的button在被点击之后将会改变这个值，为了使这个变化同步到父组件中，我们就可以使用`.sync`修饰符

```js
<template>
  <div id="app">
    现在父组件的num值为：
    {{num}}
    <hr />
	<childComponent :childNum = "num" @update:childNum = "num = $event"/>
    <!-- 可以简化为下面 -->
    <!-- <childComponent v-bind:childNum.sync="num"/> -->
  </div>
</template>

<script>
import Vue from 'vue'
Vue.component('childComponent', {
    template: `
      <div>
        子组件中num的值{{childNum}}
        <button @click = "$emit('update:childNum', childNum - 10)">点我num-10</button>
      </div>
    `,

    props: ['childNum'],
})

export default {
  name: "App",
  data(){
    return {
      num : 1000
    }
  }
};
</script>
```

我们分析一下，父组件中的`num` 通过prop将值传递给子组件。子组件获取到这个值，将这个值叫`childNum` ，然后当点击button的时候触发点击事件，emit会触发当前实例（也就是父组件）上的监听（`@update:childNum`）并且会将后面的参数传给回调。在父组件（实例）中我们得到了这个值。

以上的过程，你可以在传递prop的时候通过加上`.sync`修饰符来直接实现。