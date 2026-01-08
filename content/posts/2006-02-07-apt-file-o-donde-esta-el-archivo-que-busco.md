---
title: 'apt-file, o dónde esta el archivo que busco'
date: '2006-02-07'
tags:
- Software Libre
---

Hoy
me he encontrado con un programita que puede resultar muy útil,
apt-file. Te dice en qué paquete encontrar ese archivo que (por
ejemplo) te pide cuando intentas compilar y no sabes donde encontrarlo.

Es para Ubuntu (y Debian supongo), y es muy fácil de instalar y usar:

Instalar:

```
sudo aptitude install apt-file
sudo apt-file update
```

Buscar archivo:

```
apt-file search archivo
```