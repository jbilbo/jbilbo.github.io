---
title: 'GPG error del Apt-get'
date: '2006-02-22'
tags:
- Software Libre
---

Típico problema en Debian, Ubuntu o cualquier distribución que utilice un sistema de paquetes basado en deb con la librería apt:

```
W: GPG error: http://archive.ubuntu.com breezy-updates Release: Las siguientes firmas no son válidas: BADSIG 40976EAF437D05B5 Ubuntu Archive Automatic Signing Key 
W: Tal vez quiera ejecutar 'apt-get update' para corregir estos problemas
```

Ya lo comenté [anteriormente](/posts/2005-09-25-repositorios-para-ubuntu/), pero por fin he encontrado una solución a este error aleatorio. Se trata de hacer apt-get update con el sources.list vacío.

```
# cp /etc/apt/sources.list /etc/apt/sources.list.backup
# rm -f /etc/apt/sources.list
# touch /etc/apt/sources.list
# apt-get update
# cp -f /etc/apt/sources.list.backup /etc/apt/sources.list
```

Y fuera error. Había leído otros de cambiar el trusted.gpg, volverse
a bajar la clave, cambiar la dirección de los repositorios, etc… este
es el más fácil, rápido y efectivo.