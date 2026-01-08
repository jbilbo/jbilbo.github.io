---
title: Mega-actualizaciones…
date: '2004-03-13T11:20:00.000-08:00'
tags:
- Software Libre
---

He actualizado por fin uno de los 2 servidores de gplurv (el principal o primary). La transición era peligrosa porque, a parte de que los paquetes eran grandes, el cambio de versiones tampoco era despreciable.

Me ha dado sólo 1 problema, cuando he actualizado todo el equipo, después del reinicio para comprobar que todo va bien con todas las librerías nuevas, etc... el apache no arrancaba. ¿El problema? El módulo de php fallaba, no encontraba un archivo. Nada importante, Gentoo tiene un script llamado revdep-rebuild que te busca las "librerías rotas", que fallan en alguna llamada o dependencia a causa de una actualización de un paquete del cual depende. Ejecutando este script he visto que el módulo de php efectivamente se tenía que recompilar (y otros 3 paquetes más de paso xD).

El caso es que la transición gcc 3.2.2 a 3.3.2 también me ha dado un problema, y claro... al recompilar el módulo de php pues fallaba... Lo he solucionado temporalmente con 2 links simbólicos (feo pero funciona :D).

Esto último ha hecho que el apache estuviera parado poco menos de 2h.

Peor será cuando actualicemos el drupal, el apache1 a apache2 y la mysql de 3 a 4 ;-)

Y no quiero hablar de pasar de ISO-15 a utf-8... xDD