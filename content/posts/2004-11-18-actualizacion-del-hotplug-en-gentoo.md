---
title: Actualización del hotplug en Gentoo
date: '2004-11-17T19:36:00.000-08:00'
tags:
- Software Libre
---

Ahora el hotplug de Gentoo se ha dividido en 2 paquetes, el hotplug  (para cargar módulos una vez ha arrancado el ordenador) y coldplug (para que los arranque al inicio). Además de eso ha cambiado alguna localización/nombre de sus directorios y  ficheros de configuración.

Pasos para migrar de uno a otro:

```
emerge --sync
emerge hotplug coldplug
rc-update add coldplug boot
```

Borramos el archivo (si es que lo tenemos) isapnp.rc porque esta obsoleto y pasamos nuestro firmware (si tenemos alguno) a la nueva carpeta:

```
rm -f /etc/hotplug/isapnp.rc
mkdir /lib/firmware
mv /usr/lib/hotplug/firmware/* /lib/firmware/.
```

Por último actualizamos la configuración:

```
etc-update
```

Toda la configuración en /etc/hotplug puede ser sobreescrita con la nueva sin problemas (a no ser que vosotros mismos hayais modificado algo).

Editado: [Artículo](http://www.gpltarragona.org/node/view/320) en gpltarragona.