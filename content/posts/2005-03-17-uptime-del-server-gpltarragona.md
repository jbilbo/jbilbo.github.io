---
title: Uptime del server gpltarragona
date: '2005-03-17T11:42:00.000-08:00'
tags:
- Software Libre
---

Parece mentira que aguante todavía... ¿cuantas veces se ha caído el server de gpltarragona? Tiene sólo 64mb de RAM y es normal que cuando reciba X peticiones/minuto empiece a rascar swap... en definitiva el problema esta cuando hay un numero de peticiones alto en poco tiempo y se queda sin recursos... y entonces es cuando la mysql se suicida.

Pero mirad el uptime del servidor principal de gpltarragona (el que recibe toda la furia vuestra):

```
$ uptime
 19:34:02 up 47 days, 15:07,  1 user,  load average: 11.43, 7.07, 3.03
```

Por suerte en breve tendremos nuevo hardware y esto con suerte no sucederá (fijaos en la carga de sistema y comparadla vuestro ordenador de casa... impresionante sí xD).