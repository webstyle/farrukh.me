---
title: "Salom Supervisor!!!"
layout: post
date: 2018-02-24 00:18
image: /assets/images/supervisor.png
headerImage: true
tag:
- supervisor
- process control
star: true
category: blog
author: farrukh
description: Supervisor processlarni boshqarish haqida O'zbekcha qo'llanma.
comments: true
---

## Qisqacha
Supervisor - UNIX tizimlardagi raqamli processlarni boshqarish uchun mo'ljallangan client/server tizim hisoblanadi.
Supervisor bugungi kunda juda ko'p dasturchilar tomonidan ishlatilib kelinmoqda. Bu yangi dastur emas, allaqachon ko'p yillardan
beri ko'plab foydalanuvchilar o'z serverlarida ishlatib kelishmoqda.

## Imkoniyatlar:
#### Oson
Supervisor o'qishga va tushunishga oson bo'lgan UNIX tizimlaridagi `INI` fayllar ko'rnishida sozlanadi. Ya'ni har bitta processni 
sozlab chiqib katta vaqt olmaydi.

#### Markazlashtirilgan
Supervisor barcha processlarni bir joydan boshqarish ya'ni `{start|stop|restart}` va monitoring qilish imkoniyatini beradi.
Processlar guruhlarga bo'lingan holda yoki individual boshqarishingiz mumkin. Bularning barchasini veb interfeys orqali bajarishingiz
mumkin.

#### Mutanosiblik
Windowsdan tashqari. Linux, Mac OS X, Solaris, va FreeBSD tizimlarida bemalol ishlaydi. Supervisor Pythonda yozilgani
uchun C komilyatorni talab qilmaydi.

--
## O'rnatish
Linux uchun:

    easy_install supervisor
    
MacOS uchun:

    brew install supervisor
    
    
yoki pip orqali o'rnatishingiz ham mumkin:

    pip install supervisor



## supervisord
Supervisor serverni boshqarish uchun servis. Server process sozlamalari `/etc/supervisord.conf` joylashgan.

## supervisorctl
Supervisor CLI uskuna hisoblanadi. Bu uskuna orqali processni boshqarish mumkin bo'ladi.


## Process qo'shish!
Keling Python tilida yozilgan dasturni ishga tushurib ko'ramiz.
Yangi qoshmoqchi bo'lgan processni alohida faylga yozishimiz kerak bo'ladi. `/etc/supervisor/conf.d/my_app.conf` fayliga yozamiz:

```bash
[program:my_app]                      # dasturning nomi
directory=~/my_app                    # kodimiz joylashga papka
command=python app.py                 # ishga tushurish kerak bo'lgan buyruq
stderr_logfile=/var/log/long.err.log  # stderr(Error) yozish kerak bo'lgan log fayl
stdout_logfile=/var/log/long.out.log  # stdout yozish kerak bo'lgan log fayl
```
Faylni saqlaymiz. Yangi qo'shilgan sozlamalarni o'qib olish uchun quyidagi buyruq:
```bash
$ sudo supervisorctl reread
```
Serverda process sozlamasini yangilash uchun:
```bash
$ sudo supervisorctl update
```
Process qo'shildi endi uni bemalol boshqarishimiz mumkin. Processlarni boshqarish uchun:
```bash
$ sudo supervisorctl
my_app                      RUNNING    pid 12614, uptime 1:49:37
supervisor>
```
shunda processlar ro'yxati va holati chiqadi.

Processni to'xtatish uchun:
```bash
$ sudo supervisorctl stop my_app
```

Processni ishga tushurish uchun:
```bash
$ sudo supervisorctl start my_app
```

Processni qayta ishga tushurish uchun:
```bash
$ sudo supervisorctl restart my_app
```

Processni holatini ko'rish uchun:
```bash
$ sudo supervisorctl status my_app
```

## Web interfeys
Processlarni veb orqali boshqarish uchun `/etc/supervisor/supervisord.conf` fayliga quyidagi sozlamalarni yozing:
```bash
[inet_http_server]
port=127.0.0.1:9001
username=admin
password=1123
```
shunda http://localhost:9001 orqali `admin` logini va `123` paroli bilan kirishingiz mumkin.

![Screenshot](http://farrukh.me/assets/images/supervisor.png)
photo by http://codesamplez.com

### Foydali materiallar:
* [Process Control System Wiki](https://en.wikipedia.org/wiki/Process_control)
* [supervisord.org](http://supervisord.org/index.html)
* [Supervisor GitHub](https://github.com/Supervisor/supervisor)



