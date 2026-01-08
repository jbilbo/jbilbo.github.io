---
title: Ubuntu Hoary en un AMD64 y Release Final
date: '2005-04-07T19:10:00.000-07:00'
tags:
- Software Libre
---

Hoy he podido probar a instalar una Ubuntu con el CD de la RC (Release Candidate) y comprobar cómo funciona esta distribución con otra arquitectura diferente a la x86. Una de las cosas que me ha llamado la atención es que el LiveCD de x86 (de la versión anterior de hace 6 meses, la Warty) funciona perfectamente en la arquitectura AMD64, y es que aunque sí sabía que la compatibilidad 32-64 bits existía, como Ubuntu pone en el CD sólo compatible con x86 y los CDs de AMD64 no incluían el LiveCD (sólo instalación)... pensaba que no había todavía ninguno disponible. Pero claro, hay que pensar en una cosa compatible contra una cosa optimizada o compilada para tu arquitectura que aproveche la capacidad de un procesador de 64bits. Hoary ya tiene versión para AMD64.

En cuanto a la instalación ha ido todo como la seda menos al final, cuando ha tenido que salir el login gráfico. Ahí se ha quedado colgado, tema de la tarjeta gráfica ATI 9250 que llevaba. Se consigue compatibilidad gráfica poniendo en la línea del archivo de configuración de las X: /etc/X11/xorg.conf el driver "vesa" en vez del driver "ati" que te ponía (el fglrx propietario tampoco iba...). Por supuesto aceleración 3D no tendrá porque el driver vesa es el genérico, compatible con la mayoría de tarjetas gráficas. Aunque para trabajar en escritorio funciona a la perfección (con el doom 3 ya no tanto :P).

Por cierto, oficialmente ya es 8 de abril y [Ubuntu estrena nueva web](http://www.ubuntu.com/) (la que ganó el concurso) y oficialmente lanza la versión Final de Hoary!