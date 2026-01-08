---
title: Cuelgues con los ati-drivers
date: '2004-05-02T20:42:00.000-07:00'
tags:
- Software Libre
---

Tenía la versión estable de los drivers de ati propietarios que hay actualmente en el portage (media-video/ati-drivers-3.2.8-r1). Los drivers libres no se llevan muy bien con mi tarjeta todavía ([ATI Radeon 9200](http://dri.sourceforge.net/cgi-bin/moin.cgi/ATIRadeon?action=highlight&value=CategoryHardware#head-465a5bcb4ff2a8459736c469bfac6c242de7f3c1)), y eso que está [teóricamente soportada](http://dri.sourceforge.net/cgi-bin/moin.cgi/ATI?action=highlight&value=CategoryHardware).

No me daban ningún problema con lo básico: Las X y los juegos 2D. Pero hoy, me ha dado por probarlo durante unos 15 minutos con el juego Unreal Tournament 2004 demo (emerge ut2004-demo) y se me ha producido un cuelgue parcial del equipo (el kernel respondía, pero cuando mataba el juego el kernel también moría).

Lo probé un par de veces más y pasaba al rato, así que no era casual, era un bug.

Algunos errores:

```
[fglrx:firegl_addmap] *ERROR* cannot create different map at same offset 0xe1a22000
[fglrx:firegl_alloc_bufs] *ERROR* Unable to add buffer mapping -> inconsistent kernel data!!
```

Hice varias pruebas, pero al final lo he arreglado instalando la última versión del driver que hay actualmente en el portage (media-video/ati-drivers-3.7.6-r1).
