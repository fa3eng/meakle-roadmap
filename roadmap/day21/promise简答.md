# 你对 Promise 的了解？

1. Promise 的用途

   解决回调地狱的问题

2. 如何创建一个 new Promise（课堂里让大家背过）

   ```js
   let promise = new promise(function (resolve, reject) {
       
       let a = 1;
   
       // 随便写的条件
       if(a === 1){
           resolve();
       } else {
           reject();
       }
   })
   ```

3. 如何使用 Promise.prototype.then（可查 MDN）

   ```js
   doSomething.then(successCallback, failureCallback);
   ```

4. 如何使用 Promise.all（可查 MDN）

   ```js
   const promise1 = Promise.resolve(3);
   const promise2 = 42;
   const promise3 = new Promise((resolve, reject) => {
     setTimeout(resolve, 100, 'foo');
   });
   
   Promise.all([promise1, promise2, promise3]).then((values) => {
     console.log(values);
   });
   // expected output: Array [3, 42, "foo"]
   
   ```

5. 如何使用 Promise.race（可查 MDN）

   ```js
   const promise1 = new Promise((resolve, reject) => {
     setTimeout(resolve, 500, 'one');
   });
   
   const promise2 = new Promise((resolve, reject) => {
     setTimeout(resolve, 100, 'two');
   });
   
   Promise.race([promise1, promise2]).then((value) => {
     console.log(value);
     // Both resolve, but promise2 is faster
   });
   // expected output: "two"
   ```

   

