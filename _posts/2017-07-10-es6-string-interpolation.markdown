---
title: "ES6: String interpolation"
layout: post
date: 2017-08-10 23:02
image: /assets/images/es6-logo.png
headerImage: true
tag:
- es6
- string
- interpolation 
- javascript 
star: true
category: blog
author: farrukh
description: Simple example string interpolation in ES6
comments: true
---

## Muammo?:
EcmaScriptning eski versiyalarida *string*ning ichiga bironta o'zgaruvchi yoki funksiyadan qaytayotgan qiymati ishlatish uchun quyidagicha ko'rinishda kod yozar edik:

{% highlight raw %}
{ % gist WebStyle/f17d4bd6d5fc49c9f3c13cda18633367 % }
{% endhighlight %}


Yoki ko'p qatorli(multi line) string yozmoqchi bo'lganda esa:

{% highlight raw %}
{ % gist WebStyle/8688987639217a7fddfdaf6622513cfd % }
{% endhighlight %}

---
ES6da esa string interpolation imkoniyati qo'shildi.
Endi yuqorida ko'rsatilgan kodlarni quyidagi ko'rinishda yozish mumkin.

{% highlight raw %}
{ % gist WebStyle/88c5e5b5f77d22e469ad56f73d1f4d15 % }
{% endhighlight %}