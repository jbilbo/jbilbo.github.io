---
title: 'Actualizar a la nueva Ubuntu Breezy 5.10'
date: '2005-10-14'
tags:
- Software Libre
---

Hoy por la mañana ha salido por fin [Ubuntu Brezzy 5.10](http://www.ubuntu.com/newsitems/release510), que incluye muchas novedades destacando sobretodo Gnome 2.12.1.

Para los que tengan una versión anterior de Ubuntu (Warty 4.10 o
Hoary 5.04) y se quieran pasar a la nueva estable, he aquí las
instrucciones:

Modificar el archivo /etc/apt/sources.list. Debe contener lo siguiente, única y exclusivamente:

```
deb http://es.archive.ubuntu.com/ubuntu breezy main restricted universe multiverse
deb http://es.archive.ubuntu.com/ubuntu breezy-updates main restricted universe multiverse
deb http://security.ubuntu.com/ubuntu breezy-security main restricted universe multiverse
```

Seguimos…

![Logo Ubuntu Breezy](/images/posts/ubuntu-breezy.png)

A continuación, desde la terminal o desde el programa gráfico
Synaptic (recomendado el segundo que se supone es el “oficial de
Ubuntu”) hacemos lo siguiente:

- Si utilizamos apt-get desde la terminal:

```
apt-get update
apt-get dist-upgrade
```

- Si utilizamos apt-get desde la terminal:

```
aptitude update
aptitude dist-upgrade
```

- Si utilizamos el Synaptic:

Recargar -> Marcar las Actualizaciones -> Aplicar

También podeis utilizar tanto aptitude como el propio update-manager
(si estais en hoary). En fin, a disfrutar con la nueva Breezy, si
teneis algún problema ponerlo por aquí en los comentarios y
intentaremos ayudar.

PD: [Artículo en GPLTarragona](http://www.gpltarragona.org/node/view/393).