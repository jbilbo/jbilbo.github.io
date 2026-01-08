---
title: 'Repositorios para Ubuntu'
date: '2005-09-25'
tags:
- Software Libre
---

**Si queremos estar en la ahora estable hoary**, el fichero /etc/apt/sources.list tiene que tener lo siguiente, y no más:

```
deb http://archive.ubuntu.com/ubuntu/ hoary main restricted universe multiverse
deb http://security.ubuntu.com/ubuntu/ hoary-security main restricted universe multiverse
deb http://archive.ubuntu.com/ubuntu/ hoary-updates main restricted universe multiverse
#BACKPORTS
#deb http://archive.ubuntu.com/ubuntu hoary-backports main universe multiverse restricted
#deb http://ubuntu-backports.mirrormax.net/ hoary-extras main universe multiverse restricted
```

Lo de Backports lo tengo comentado porque a lo mejor nos interesa
para algún paquete puntual. Tiene que estar siempre comentado, aunque
no lo utiliceis ahora no va mal tenerlo ahí para el futuro.

**Si queremos estar en breezy** (rama inestable ahora, y que lleva Gnome 2.12), el fichero /etc/apt/sources.list tiene que tener lo siguiente, y no más:

```
deb http://es.archive.ubuntu.com/ubuntu breezy main restricted universe multiverse
deb http://es.archive.ubuntu.com/ubuntu breezy-updates main restricted universe multiverse
deb http://security.ubuntu.com/ubuntu breezy-security main restricted universe multiverse
```

Podeis ir directamente al fichero /etc/apt/sources.list y
modificarlo con lo que he puesto arriba, no hace falta hacerlo desde
ninguna interfície gráfica, cuando modifiquemos el fichero, las
interfícies lo leeran y lo interpretaran correctamente.

**Actualización (29/09/2005)**: [hoary-backports se vuelve oficial](/posts/2005-09-29-actualizar-vuestros-backports/).