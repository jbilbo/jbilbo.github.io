---
title: "Salió Ubuntu 6.06 LTS, nombre en clave Dapper Drake"
date: 2006-06-01T17:03:00+02:00
tags: ["Ubuntu", "Linux", "Software Libre"]
---

Por fin salió "la dapper", el [anuncio oficial](https://lists.ubuntu.com/archives/ubuntu-announce/2006-June/000083.html) y el [enlace a los mirrors](http://www.ubuntu.com/download) donde esta disponible para su descarga. Hay un montón, sólo ha llegado a saturarse el primero de la lista al mediodía.

{{< figure src="/images/posts/606lts.png" alt="Ubuntu 6.06 Long Term Support" >}}

Esta versión de Ubuntu [es especial](http://www.ubuntu.com/news/606released), tendrá soporte de 3 años para paquetes de escritorio (ubuntu-desktop) y 5 para paquetes de servidor (ubuntu-server), es lo que llaman "Long Term Support" y por eso lleva de coletilla las siglas LTS.

**Características de esta versión**

*En el CD Desktop:*

* Un nuevo, y rápido, instalador gráfico que se ejecuta desde el LiveCD

* Inicio y login más rápido, se nota que es más rápido al arrancar que la Breezy.

* Organización del menú simplificado.

* Proceso de apagado gráfico (al salir desde Gnome)

* Fácil acceso a la administración de energía con el nuevo Gnome Power Manager.

* Soporte mejorado para el video playback.

* Fácil administración de la redes Wireless (conectarse a diversos AP, roaming... etc) con el programa NetworkManager, no esta instalado por defecto.

* OpenOffice.org 2.0.2, X.org 7.0

* Soporte para actualizaciones de traducción durante la vida de Dapper.

*En el servidor:*

* Nuevos kernels dirigidos a plataformas específicas para servidores. Estan optimizados de manera diferentes que los "Desktop", dan mejores resultados en aplicaciones de servidor.

* Kernel "BigIron", orientado a sistemas con más de 8 CPUs (ES7000 / Summit / BIGSMP).

* Turn-key LAMP installation for this common deployment scenario

* Soporte mejorado para clusters i SANs

* Mejoras para los Thin client, incluyendo arranque más rápido, proceso gráfico de arranque, requerimientos de memoria reducidos y soporto de dispositivos de sonido.

*Instalación y actualizaciones:*

* Ubunu puede ahora instalarse en dispositivos USB, como discos duros extraíbles y memorias flash, usando el instalador en modo-texto (text-mode installer).

* Una [nueva herramienta de actualización](/posts/2006-04-21-actualizar-a-dapper-desde-breezy-de-manera-facil/) esta disponible, para upgrades simples, limpios y consistentes de una versión de Ubuntu a la siguiente, empezando desde la versión 5.10 (Breezy).

* El instalador alternativo (el que no va por LiveCD), ahora se completa sólo con 1 reinició (cuando ya esta el sistema instalador). Esto hace mucho más rápido y simple el proceso de instalación.

*"Por debajo"*

* GCC 4.0.3
* glibc 2.3.6
* Linux 2.6.15.6
* Infrastructura nueva en el live CD para mejorar el rendimiento, usabilidad i eficiencia en el espacio utilizado.
* Gran mejora en la infrastructura de detección y activación de hardware.
* El PATH del sistema esta ahora en un solo sitio: /etc/environment. Para mejor administración.

{{< figure src="/images/posts/ubuntu-cof-606.png" alt="Ubuntu Dapper Drake" >}}

Y eso es todo, incluyendo la actualización de todos los paquetes de Ubuntu que gracias al esfuerzo de Debian primero y el equipo de Ubuntu después estan disponibles en los respositorios oficiales.

Las [Release Notes](http://wiki.ubuntu.com/DapperReleaseNotes) oficiales de la salida.
