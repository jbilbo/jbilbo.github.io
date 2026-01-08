---
title: 'ORA-27125: unable to create shared memory segment'
date: '2004-07-08T09:17:00.000-07:00'
tags:
- Software Libre
---

Peazo de título...

Es un error de **Oracle Database 10g** que me dio al intentar instalarla en **SuSE 9.1 Personal Edition** con **kernel 2.6.5-7.95**. Ocurre en el apartado de Asistente de configuración de Bases de Datos, es un apartado opcional pero supongo que la mayoría quiere completarlo.

Solución:

```
su - root
echo "1" > /proc/sys/vm/disable_cap_mlock
```

Y volverlo a hacer. Se puede reintentar (retry).
[Más info](http://forums.oracle.com/forums/thread.jsp?forum=135&thread=233621&message=688804)