---
title: 'Audio en Dell XPS Studio 16 bajo Linux'
date: '2010-01-07'
tags:
- Linux
- Software Libre
---

Esto es en concreto para Ubuntu 9.10 (Karmic Koala), supongo que en versiones posteriores (con Alsa más actualizado) no hará falta. Ahora mismo, para que el audio funcione se tiene que poner en:

```bash
$ gksudo gedit /etc/modprobe.d/alsa-base.conf
```

la siguiente linea al final del archivo:

```
options snd-hda-intel model=dell-m6
```
