---
title: "JavaScriptda funksiya e'lon qilish usullari (Uzbek language)"
layout: post
date: 2017-08-1 23:56
image: /assets/images/markdown.jpg
headerImage: false
tag:
- javascript
- function
star: true
category: blog
author: farrukh
description: JavaScript funksiya e'lon qilish usullari
comments: true
---

Ushbu kichik maqolada JavaScriptda funksiyalarni e'lon qilishning bir necha usullarini ko'rib chiqamiz

---

Misol 1:
```javascript
function greeting(name) {
    return `Hello ${name}`;
}
```

Misol 2:
```javascript
const greeting = function(name) {
    return `Hello ${name}`;
}
```

Misol 3:
```javascript 
const greeting = name => `Hello ${name}`;
```

Misol 4:
```javascript
const greeting = anotherGreeting;

function anotherGreeting(name) {
    return `Hello ${name}`;
}
```

---
### Foydali ma'lumotlar
- [function declaration](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Statements/function)