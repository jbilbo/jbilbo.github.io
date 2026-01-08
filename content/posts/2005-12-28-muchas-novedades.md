---
title: '¡Muchas novedades!'
date: '2005-12-28'
tags:
- Software Libre
---

Tenemos [Wordpress 2.0](http://wordpress.org/). Muchas mejoras internas, editor del tipo openoffice, caché integrando, trackback por Ajax… etc. [Guía para actualizar](http://codex.wordpress.org/Upgrading_WordPress).

Yo creo que esperaré un poquito antes de actualizar…

Y ya tenemos aMSN 0.95 (con soporte webcam). [Nuevo diseño de la página](http://amsn.sourceforge.net/) (que a mi con Firefox 1.07 desde Linux no se me visualiza del todo bien esa barra “flotante” de la derecha). [Mirror](ftp://photojerk.com/pub/) con los paquetes para la mayoría de distribuciones. Para Ubuntu haced lo siguiente para tened listas las dependencias de amsn:

```
aptitude install amsn
apt-get remove amsn
dpkg -i paquete-que-te-hayas-bajado
```

Hay paquete de GTKpod 0.99.2 (soporta video para los iPod 5G) para probar desde el foro de Backports de Ubuntu:

Instalado con “sudo dpkg -i” los siguientes paquetes

- [libgpod 0.3.0](http://samztercomix.com/kim/tech/linux/programs/gtkpod_0.99.2-1_i386.deb)

- [gtkpod 0.99.2](http://samztercomix.com/kim/tech/linux/programs/libgpod_0.3.0-1_i386.deb)

Por otra banda también hay [nueva versión de las X.org](http://www.x.org/) con novedades en el soporte 3D de las nuevas tarjetas gráficas ATI. Veremos si por fin tienen un soporte libre bueno.

Y una nueva novedad para Gnome 2.14, poder establecer permisos recursivamente de manera fácil:

![Permisos recursivos en Gnome](/images/posts/gnome-permisos-recursivos.png)