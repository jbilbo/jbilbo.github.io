---
title: 'jemerge: Rama estable e inestable en Gentoo'
date: '2004-06-07T20:49:00.000-07:00'
tags:
- Software Libre
---

Gentoo te permite estar en la rama estable y en la inestable a vez. Es decir, puedes tener la última versión del gaim y el amule pero estar usando un sistema estable con sus glibc, gcc y demás de la rama estable. Para emerger un paquete en su últimísima versión (rama inestable), ya he hablado del [emergetest](/posts/2004-06-03-emergetest/).

El problema radica cuando, a parte de emerger un paquete (por ejemplo "mono") de la rama inestable, también lo haces con una dependencia de ese paquete de la rama inestable (por ejemplo "gtk-sharp").

El portage en ese caso todavía no trabaja bien cuando intentamos actualizar todo el sistema, por sus (buenas) razones, que no explicaré aquí, pero que al fin y al cabo no nos va bien. Normalmente actualizamos con un "emerge -pUD world" para quedarnos con los últimos paquetes "-U" y que no nos bajen la versión... el caso es que con este problema mencionado el -U peta, sólo queda el -u. Y pasan cosas como esta:

```
valinor ~ # emerge -puD world

These are the packages that I would merge, in order:

Calculating world dependencies ...done!
[ebuild     UD] sys-libs/zlib-1.1.4-r2 [1.2.1-r2] -debug  0 kB
[ebuild     U ] app-crypt/hashalot-0.2.0 [0.1.0]  0 kB
[ebuild     UD] x11-base/opengl-update-1.5 [1.7]  [empty/missing/bad digest]
[ebuild     U ] sys-apps/baselayout-1.9.4-r2 [1.9.4-r1] -bootstrap -build -livecd -(selinux) -static  0 kB
[ebuild  N    ] x11-base/xfree-4.3.0-r5  -debug  16,984 kB
[ebuild  N    ] media-video/ati-drivers-3.2.8-r1  +gnome -kde -qt  0 kB
[ebuild     UD] media-libs/sdl-mixer-1.2.5-r1 [1.2.5-r2] +mikmod +mpeg +oggvorbis  0 kB
[ebuild     UD] x11-libs/wxGTK-2.4.1-r1 [2.4.2] +gtk2 +nls +odbc +opengl  0 kB
[ebuild     UD] dev-python/wxPython-2.4.1.2 [2.4.2.4] +gtk2 +jpeg +opengl +png +tiff  0 kB
[ebuild     UD] media-video/camserv-0.5.0 [0.5.1-r2]  0 kB
[ebuild     UD] media-fonts/sharefonts-0.10-r1 [0.10-r3]  0 kB
[ebuild  N    ] dev-libs/libgpg-error-0.6  +nls  0 kB
[ebuild     U ] dev-libs/libgcrypt-1.1.94 [1.1.12] -doc +nls  827 kB
[ebuild     UD] app-text/gtranslator-0.43 [1.0] +nls  0 kB
[ebuild     UD] dev-libs/icu-2.6 [2.8]  0 kB
[ebuild     UD] net-p2p/amule-1.1.0 [2.0.0_rc3]  0 kB
[ebuild     UD] media-sound/rhythmbox-0.6.1-r1 [0.8.3] -faad -flac +mad +oggvorbis -xine  0 kB
[ebuild     U ] dev-util/glade-2.0.1 [2.0.0-r1] +gnome -gnomedb  1,867 kB
[ebuild     UD] dev-dotnet/mono-0.28 [0.95]  0 kB
[ebuild     UD] net-im/amsn-0.90 [0.92] +gnome -imagemagick +imlib -kde +xmms  0 kB
[ebuild     UD] net-www/netscape-flash-6.0.81 [7.0.25] +gtk  0 kB
[ebuild     U ] app-cdr/k3b-0.11.10 [0.11.9] -debug -dvdr +encode -flac -kde +mad -monkey +oggvorbis  3,543 kB

Total size of downloads: 23,222 kB

valinor ~ #
```

De todos estos, sólo me interesa actualizar 6. ¿Qué hago? La única forma es hacerlo uno a uno, copiando-pegando y luego "emerge paquete1 paquete2..." no-óptimo xD.

El caso es que pululaba por el [foro](http://forums.gentoo.org/viewtopic.php?t=45827) de Gentoo un par de scripts, el "femerge" y el "pfilter" y he retocado el primero para que me solucione ese problema en concreto. Tal y como estaba no me lo hacía bien, pero ahora funciona a la perfección...

Como el script ha cambiado bastante, le he puesto **jemerge**. Y **basta con ejecutarlo en modo root sin ningún parámetro para que funcione. Tiene como dependencia el pfilter.**

![jemerge](/images/posts/jemerge1.jpg)

**Descarga**: [jemerge](/files/jemerge) - [pfilter](/files/pfilter)

![jemerge](/images/posts/jemerge2.gif)

**Instalación**: Meter jemerge y pfilter en /usr/bin (por ej.), o en donde querais si sabeis lo que haceis... mientras esté en el path, ya vale.
**Uso**: Ejecutar "jemerge". Saldrá una pantalla para seleccionar (en ncurses) los paquetes a instalar (o bajarse únicamente).