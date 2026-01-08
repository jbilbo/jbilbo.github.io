---
title: Hoy tocaba romper
date: '2004-04-05T19:36:00.000-07:00'
tags:
- Software Libre
---

Me he puesto a solucionar un problema con el ALSA de mi ordenador de sobremesa y de paso también decidido a pasar al kernel 2.6.5. Y es que mi hardware es un poco conflictivo: chip de placa base basada en SiS (chip, tarjeta de sonido, ethernet, agp...).

El caso es que ALSA no me funciona no sé por qué. Lo tenía funcionando hace unos meses pero un día dejó de oírse... (estas cosas no las soporto, arg :P) y como solución rápida puse mi gran amigo el módulo OSS. Hoy me he puesto con esto y me he vuelto a fijar (en su día también lo vi) que no puedo subir el volumen (con alsamixer) del PCM. Estoy seguro de que por ahí van los tiros... pero de ahí a arreglarlo... :P

Estuve probándolo con el Alsa del kernel 2.6.5, después lo deshabilité y jugué con el Alsa del portage... y nada, todo igual, imposible subir el volumen del PCM. Sigo sin Alsa :( , menos mal que el módulo OSS me funciona sin problemas.

Después de esto, y de poner FrameBuffer con el 2.6.5 (recordad que el "vesa" del 2.4 en los 2.6 se llama "vesafb" :P) me di cuenta de que no podía arrancar las X :O (también sin causa aparente, argg xD)

He estado toda la tarde mirando, probando.... que si el driver propietario de la ATI (fglrx), que si el libre (radeon)... que si el estándar (vga)... nada. Por el camino me he encontrado con fallos, he ido aprendiendo algunas cosas del kernel 2.6 y la ATI... he vuelto al kernel 2.4 para ver si era la causa (no lo era)... hasta que al final me he dado cuenta que no era problema de las X, sino el Gnome!!! Los logs, que eran mínimos... solían dar referencias a problemas con las X... pero ahora entiendo que eran "cosméticos" y que el hecho de no dar pistas en los logs era porque realmente las X arrancaban bien. No me he dado cuenta en principio que era fallo de Gnome porque no tardaba mucho en "petar"... qué fallo por mi parte no cerciorarme!

Como tengo el KDE para pruebas, lo he probado y sí... sin problemas. Y ahora... qué leches le ha pasado al Gnome! Seguro que se ha confabulado con el Alsa :)

**Actualización**: Era verdad, se habían confabulado! :-) El hecho de quitar alsa repercute en recompilar los paquetes que tienen actualmente soporte (y gnome-session, lo primero que se ejecuta para arrancar gnome, casualmente es uno de ellos).

Algunos recursos que he encontrado en mi aventura:

- [Vesa Framebuffer y ATI, problema con mtrr](http://www.rage3d.com/board/showthread.php?s=6676f99a92d070b585bd04ae26596fe4&threadid=33736241)
- [Problemas con 2.6 input drivers](http://kerneltrap.org/node/view/2199)
- [Gentoo ATI Radeon FAQ](http://odin.prohosting.com/wedge01/gentoo-radeon-faq.html)