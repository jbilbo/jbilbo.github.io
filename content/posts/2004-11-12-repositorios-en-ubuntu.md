---
title: Repositorios en Ubuntu
date: '2004-11-11T20:18:00.000-08:00'
tags:
- Software Libre
---

Una cosa importantísima para tener una distribución "sana" y que no "se resfrie" (sobretodo ahora con este tiempo... xD) es tener bien puestos los repositorios y updatear/actualizar cada cierto tiempo no far far away...<br/><br/>Ahora mismo, lo correcto en Ubuntu sería tener estos repositorios en el fichero /etc/apt/sources.list:<br/><br/><pre>deb http://archive.ubuntu.com/ubuntu/ warty main restricted<br/>deb http://archive.ubuntu.com/ubuntu/ warty universe multiverse<br/>deb http://security.ubuntu.com/ubuntu/ warty-security main restricted<br/>deb http://www.getsweaaa.com/~tseng/ubuntu/debs/ ./</pre><br/><br/>El último de ellos creo que sólo lo tengo para <a href="http://www.gpltarragona.org/node/view/310">tomboy</a>, así que si no os interesa esa aplicación podeis quitarlo.<br/><br/>Por último, para algún paquete quizás os interese <a href="http://jhernandez.gpltarragona.org/blog/archives/000232.html">este post</a> también.