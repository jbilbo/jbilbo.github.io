---
title: Abrir elinks desde Mozilla Firefox con mldonkey
date: '2004-11-15T06:01:00.000-08:00'
tags:
- Software Libre
---

Hoy he descubierto el plugin que te permite hacerlo! Hace un tiempo busqué información y no encontré nada pero hoy de casualidad he visto que venía con el mldonkey mismo lo que pasa que una versión vieja.

Para que funcione con mozilla 0.9.3 (la de ubuntu estable), aunque supongo que también irá con mozilla 1.0, basta con bajarse la última versión de su web:

[Mozilla MLdonkey Protocol Handler](http://www.informatik.uni-oldenburg.de/~dyna/mldonkey/)

El elink se transfiere directamente a mldonkey a través de su interfície web, cuando hagamos click a un "ed2k://"  nos preguntará el password de nuestro cliente mldonkey (si es que le hemos puesto). Al ponerlo correctamente, saldrá una ventana (pop-up) donde pondrá "done". Accedemos a mldonkey con nuestra interfície favorita y veremos que el elink ya esta puesto para bajar.