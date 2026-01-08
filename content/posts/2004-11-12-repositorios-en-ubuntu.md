---
title: Repositorios en Ubuntu
date: '2004-11-11T20:18:00.000-08:00'
tags:
- Software Libre
---

Una cosa importantísima para tener una distribución "sana" y que no "se resfrie" (sobretodo ahora con este tiempo... xD) es tener bien puestos los repositorios y updatear/actualizar cada cierto tiempo no far far away...

Ahora mismo, lo correcto en Ubuntu sería tener estos repositorios en el fichero /etc/apt/sources.list:

```
deb http://archive.ubuntu.com/ubuntu/ warty main restricted
deb http://archive.ubuntu.com/ubuntu/ warty universe multiverse
deb http://security.ubuntu.com/ubuntu/ warty-security main restricted
deb http://www.getsweaaa.com/~tseng/ubuntu/debs/ ./
```

El último de ellos creo que sólo lo tengo para [tomboy](http://www.gpltarragona.org/node/view/310), así que si no os interesa esa aplicación podeis quitarlo.

Por último, para algún paquete quizás os interese [este post](/posts/2004-11-09-w32codecs-y-libdvdcss2-en-ubuntu/) también.