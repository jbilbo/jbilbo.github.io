---
title: Juegos OpenGL y Linux
date: '2004-04-11T20:08:00.000-07:00'
tags:
- Software Libre
- Videojuegos
---

Me he puesto a probar los juegos Postal2 y Unreal Tournament 2004 (las demos). Está en el portage:

```
emerge postal2mpdemo
emerge ut2004-demo
```

La cuestión es que en mi sobremesa (ATI Radeon 9200 con drivers propietarios "ati-drivers") se descuadraba toda la imagen al empezar el juego... no se colgaba pero era prácticamente imposible continuar a no ser que con mucha suerte encontraras la tecla "salir" del juego :).

Y en mi portátil (ATI Mobility 7500 con drivers libres xfree-drm integrados en el kernel 2.6.5) se visualizaba correctamente la imagen pero ocurrían un cúmulo de errores gráficos que hacían el juego igualmente injugable.

Buscando por los foros he encontrado el fallo. Es el siguiente:

En los binarios de los juegos (tanto el ut2004 como el postal2 y quizás más) te ponen la librería "libSDL-1.2.so.0" precompilada dentro del mismo paquete. Eso es lo que causa los errores gráficos, la solución es hacer un link simbólico a nuestra librería de sistema "libSDL-1.2.so.0". Así por ejemplo en el ut2004 debemos hacer en modo root:

```
cd /opt/ut2004-demo/System/
mv libSDL-1.2.so.0 libSDL-1.2.so.0.bak
ln -s /usr/lib/libSDL-1.2.so.0 libSDL-1.2.so.0
```

Con el postal2 igual, sólo que el archivo libSDL se encuentra en "/opt/postal2mpdemo/System/".

PD: Por cierto, no he dicho nada pero el Postal2 es muyyy fuerte... demasiado fuerte :) "as violent as you are" dice el lema... no sé no sé...
