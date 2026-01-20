---
title: "Extensión de audio mpc en GNU/Linux"
date: 2005-09-10T17:00:00
tags: ["Linux", "ubuntu"]
draft: false
---

He compilado el plugin para [Beep Media Player](http://www.sosdg.org/~larne/w/BMP_Homepage) de la extensión "mpc" ([+ info de BMP](http://www.marblestation.com/blog/?p=367)).
Se necesita la librería [libmpcdec](http://www.musepack.net/index.php?pg=src) y el propio [plugin para bmp](http://www.musepack.net/index.php?pg=lin) (también esta para xmms).

Si teneis Ubuntu no hace falta compilar, aprovecharemos los .deb del proyecto [Backports](http://backports.ubuntuforums.org/).

Abrimos /etc/apt/sources.list y añadimos:

```
#BACKPORTS
deb ftp://ftp2.caliu.info/backports/ hoary-backports main universe multiverse restricted
deb http://ubuntu-backports.mirrormax.net/ hoary-extras main universe multiverse restricted
```

Y ahora instalamos:

```
apt-get update
apt-get install bmp-musepack
```

Para xmms es "xmms-musepack".

Ahora quitamos las lineas de antes del fichero /etc/apt/sources.list y hacemos:

```
apt-get update
```

Hago esto porque no quiero que me actualice el resto de paquetes que tengo, sólo quiero el plugin y ya esta, el resto de mi sistema seguirá siendo "hoary".
