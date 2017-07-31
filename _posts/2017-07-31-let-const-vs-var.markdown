---
title: "let, const vs var (Uzbek language)"
layout: post
date: 2017-07-31 23:50
image: http://www.jstips.co/assets/images/logo.svg
headerImage: false
tag:
- javascript 
- ecmascript6
- es6
- let
- const
- var
star: true
category: blog
author: farrukh
description: ES6dagi let va constlarni vardan farqi
comments: true
---

# let, const vs var:

ES6da o'zgaruvchilarni e'lon qilish uchun uchun yangi let va constlarni qo'shilgani bilsangiz kerak.
Ho'sh ularni oddiy vardan nima farqi bor ekan ? 

---
#### let - scope ichida lokal o'zgurchi yaratish mumkin
1 misol:
```javascript
var a = 10;
if (true) {
    let a = 5;
    console.log(5); // 5
}
console.log(a); // 10
```

2 misol:
```javascript
var a = 2;
{
    let a = 3;
    console.log( a ); // 3
}
console.log( a ); //2
``` 

3 misol:
```javascript
let (a = 2, b, c) {
    // .. 
}
```

4 misol:
```javascript
{
    console.log(a); // o'zgaruvchining qiymati hali aniqlanmagan
    console.log(b); // ReferenceError o'zgaruvchi hali e'lon qilinmagan

    var a;
    let b;
}
```
---
#### const - o'zgaruvchini konstanta ko'rinishida ishlatish mumkin
1 misol: 
```javascript
const a = 1;

a = 2; // TypeError!
```
2 misol: 
```javascript
{
    const a = [1, 2, 3];
    a.push(4);
    console.log(a); // [1, 2, 3, 4];

    a = 1; // TypeError!
}
```
---
### Foydali ma'lumotlar
- [ES6 & Beyond](https://github.com/getify/You-Dont-Know-JS/tree/master/es6%20%26%20beyond)
- [learn.javascript.ru](http://learn.javascript.ru/let-const)