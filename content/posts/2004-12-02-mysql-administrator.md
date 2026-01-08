---
title: MySQL Administrator
date: '2004-12-01T21:53:00.000-08:00'
tags:
- Software Libre
---

La interfície gráfica definitiva para MySQL. Tiene licencia GNU GPL y esta hecha por la empresa MySQLAB, los propios creadores de MySQL.

Desde la misma interfície, es capaz de realizarse todas las tareas de administración de forma sencilla, bonita y rápidamente. He aquí una captura en funcionamiento:

[![mysql administrator](/images/posts/mysqladministrator-thumb.png)](/images/posts/mysqladministrator.png)

Pàgina web:
http://www.mysql.com/products/administrator/

Descarga:
http://dev.mysql.com/downloads/administrator/1.0.html

Versión: Linux (x86, glibc 2.3) 1.0.15 2.2M

```
$ tar -zxvf mysql-administrator-1.0.15-linux.tar.gz
$ sudo -s
# mv mysql-administrator /opt/
# apt-get install libgtkmm2.0-1c102
$ cd /opt/mysql-adminstrador/bin
$ ./mysql-administrator
```

Para Gentoo, desde hoy mismo existe un ebuild, pero esta hard-masked. Hay que introducirlo en el fichero /etc/portage/package.mask (buscad otros posts en mi blog donde se explica).

Editado: [Artículo](http://www.gpltarragona.org/node/view/327) en gpltarragona.