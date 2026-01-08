---
title: my first patch
date: '2004-06-15T11:58:00.000-07:00'
tags:
- Software Libre
---

<http://bugs.gentoo.org/show_bug.cgi?id=53984>

**Gnome 2.6.2**

Se estan haciendo los tarballs... sale mañana ;-). En el rama del portage estable seguimos con la 2.6 (eso sí, sin fallos... bastante "estable").
En [breakmygentoo](http://www.breakmygentoo.net/) hay ebuilds para el Gnome 2.7.1

**PFC**

Hoy he empezado mi Proyecto final de carrera, que tendrá que ver con el ERP Open Source [Compiere](http://www.compiere.org/).

**Recordatorio SysCtrl**

En la [web](http://linuxreviews.org/news/2004-06-11_kernel_crash/index.html) donde explican el fallo de seguridad del kernel de linux también he encontrado lo que serían los pasos a seguir (yo sólo hacía S-U-B) en caso de un cuelgue de Linux que te imposibilitará escribir ni hacer nada (normalmente el kernel sigue vivo):

```
# Alt-SysRq-R (keyboard in raw mode)
# Alt-SysRq-S (save unsaved data to disk)
# Alt-SysRq-E (send termination signal)
# Alt-SysRq-I (send kill signal)
# Alt-SysRq-U (remount all mounted file systems)
# Alt-SysRq-B (reboots the system)
```

Se tiene que tener activado en el kernel el soporte (Kernel hacking -> Magic SysRq key)

**Pivot**

[Pivot](http://www.pivotlog.net/) es un sistema blog (como wordpress o Movable type) con licencia GPL. No necesita de BD... le estoy echando un vistazo, a ver si es la alternativa a MT que estoy buscando.

**Mozilla Firefox 0.9**

Ha [salido](http://www.mozilla.org/products/firefox/) hoy. Todavía no esta en el portage.