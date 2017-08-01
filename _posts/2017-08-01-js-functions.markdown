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
{% highlight js %}
function greeting(name) {
    return `Hello ${name}`;
}
{% endhighlight %}

Misol 2:
{% highlight js %}
const greeting = function(name) {
    return `Hello ${name}`;
}
{% endhighlight %}

Misol 3:
{% highlight js %} 
const greeting = name => `Hello ${name}`;
{% endhighlight %}

Misol 4:
{% highlight js %}
const greeting = anotherGreeting;

function anotherGreeting(name) {
    return `Hello ${name}`;
}
{% endhighlight %}

---
### Foydali ma'lumotlar
- [function declaration](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Statements/function)