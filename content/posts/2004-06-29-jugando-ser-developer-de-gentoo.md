---
title: Jugando a ser developer de Gentoo
date: '2004-06-28T15:31:00.000-07:00'
tags:
- Software Libre
---

El sábado tenía un poco de tiempo libre así que me puse a intentar "devolver algo a la comunidad" (la frase típica xD). No es simple contribución como podría ser una donación o algo así. Simplemente si utilizas una distribución cada día y aprendes y trabajas con ella... qué menos que si encuentras un error lo reportes (y si sabes la solución aún mejor) para que cada día sea mejor distribución.

Lo primero que hice fue corregir un pequeño error en el ebuild de [K3B](http://www.k3b.org). Supongo que para KDE debe ir perfecto, pero para los que tiene las USE -kde -qt y +gnome no se ve el icono gráfico en el menú y en la compilación da un pequeño error al intentar mover un archivo que sólo existe si tienes la USE +kde (aunque deja instalar sin problemas).
Mejorar un ebuild es muy importante, porque cuando cambian de versión los programas no se utilizan ebuilds nuevos, casi siempre se reutilizan y se modifican mínimamente (actualizando dependencias, añadiendo nuevas, quitando viejas... etc). Por lo tanto si hay un pequeño error se va arrastrando todas las versiones.
En el bugzilla postee [el bug](http://bugs.gentoo.org/show_bug.cgi?id=55272) con el parche para la última versión.

Siguiendo con el k3b, también hice parches para todas las versiones añadiendo la USE "arts" para que se pueda compilar sin soporte si se quiere como se indicaba en [este bug](http://bugs.gentoo.org/show_bug.cgi?id=53724). La opción es perfecta, porque te permite compilarlo sin tener instalado arts, pero si lo tienes cuando ejecutas el sonido él lo detecta y lo hace servir. Si no lo tienes no ejecutará ningún sonido simplemente. Así que no afecta a la situación actual si te va bien.

Luego me di una vuelta por bugzilla y ayudé en unos cuantos bugs. Parche [por aquí](http://bugs.gentoo.org/show_bug.cgi?id=55131), parche por allá y un par de comentarios de duplicados ([este](http://bugs.gentoo.org/show_bug.cgi?id=55132) es gracioso xD) y de [soluciones](http://bugs.gentoo.org/show_bug.cgi?id=55257) a errores... y a dormir con la conciencia tranquila :-)

El domingo reporté un [bug](http://bugs.gentoo.org/show_bug.cgi?id=55332) sobre gtranslator también.

**Eclipse 3.0**

Por fin ha salido la nueva versión de eclipse. En el portage está hard masked la versión 3.0rc3 aunque estan a punto de quitarla porque a mi me funciona muy bien con la sun-jdk estable. Por ahora paso de blackdown, da más problemas.

**El juego de Ripley**

Me la alquilé en DVD. Horrible. Larga, pesada, aburrida... un rollazo. Cuando no gusta no gusta... me esperaba algo más "inteligente" pero nada... :-(

**Calificación 1/10**