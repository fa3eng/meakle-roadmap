# call、apply、bind 的用法分别是什么？

## Function.prototype.call()

`call()` 方法使用一个指定的 `this` 值和单独给出的一个或多个参数来调用一个函数。

```js
function.call(thisArg, arg1, arg2, ...)
```

## Function.prototype.apply()

`apply()`方法调用一个具有给定`this`值的函数，以及以一个数组的形式提供的参数。

```js
function.apply(thisArg, [argsArray])
```



> apply和call的区别只有一个，apply接受的是参数是一个数组，call接受的参数是一个参数列表。

## Function.prototype.bind()

`call`和`apply` 都是改变函数的`this`。 `bind`会创建一个新的函数，并且给这个函数绑定一个指针。

`bind()` 方法创建一个新的函数，在 `bind()` 被调用时，这个新函数的 `this` 被指定为 `bind()` 的第一个参数，而其余参数将作为新函数的参数，供调用时使用。

