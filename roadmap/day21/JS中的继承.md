# 如何理解 JS 的继承？

## 基于原型的继承

```js
function Person(name, age){
    this.name = name || 'unName';
    this.age = age || 0;
}

function Student(name){
    this.name = name;
    this.score = 80;
}

Student.prototype = new Person();
```

## 基于 class 的继承

```js
class Person {
    constructor(name, age){
        this.name = name || 'default';
        this.age = age  || 0;
    }

    getName(){
        console.log(this.name);
    }

    getAge(){
        console.log(this.age);
    }
}

class Student extends Person {
    constructor(name, score){
        super(name);
        this.score = score;
    }

    getAll(){
        console.log(`name:${this.name}, age:${this.age}, score:${this.score}`);
    }
}

const meakle = new Student('meakle', 90);
meakle.getAll();
```

