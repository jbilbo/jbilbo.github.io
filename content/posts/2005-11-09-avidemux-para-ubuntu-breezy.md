---
title: 'Avidemux para Ubuntu Breezy'
date: '2005-11-09'
tags:
- Software Libre
---

Si
hay algún editor de video comparable a virtualdub para Linux, ese es
avidemux. Quería probarlo para ver sus posibilidades pero no existe
paquete para Ubuntu Breezy, sólo para la nueva Dapper.

El equipo de Backports de Ubuntu, aunque todavía no hayan montado un
repositorio para Breezy por la poca cantidad de paquetes nuevos que hay
en dapper, siguen muy activos y la prueba esta en que [he sugerido un backport de Avidemux](http://ubuntuforums.org/showpost.php?p=475335&postcount=17) por la mañana y esta noche [Seth ya lo tenía](http://ubuntuforums.org/showpost.php?p=476137&postcount=23) listo para testear! Increíble :D

Yo lo he probado por encima y funciona bien, quien lo pruebe que diga si le ha ido bien o no.

[Descargar Paquete .deb de Avidemux](http://sethkinast.com/ubuntu/breezy/backports/avidemux_2.0.42-0.0ubuntu3%7Eubp5.10_i386.deb)

Instrucciones para instalar:

```
sudo dpkg -i avidemux_2.0.42-0.0ubuntu3~ubp5.10_i386.deb
```