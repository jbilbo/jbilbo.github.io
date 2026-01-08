---
title: w32codecs y libdvdcss2 en Ubuntu
date: '2004-11-08T16:17:00.000-08:00'
tags:
- Software Libre
---

Hoy me he dado cuenta de que estos 2 paquetes tan problemáticos como necesarios no estan dentro del repositorio multiverse de Ubuntu todavía. No sé si es que no los pondran o que todavía no les ha dado tiempo, pero para poder instalarlos actualmente se necesita el respositorio de marillat:

```
URI:            ftp://ftp.nerim.net/debian-marillat/
Distribution:   stable
Section(s):     main
```

Podeis encontrar toda la info en el [wiki de Ubuntu](https://www.ubuntulinux.org/wiki/RestrictedFormats).

Instrucciones rápidas (en modo root):

```
vi /etc/apt/sources.list
```

Añadimos el repositorio:

```
deb ftp://ftp.nerim.net/debian-marillat/ stable main
```

Actualizamos la lista de paquetes e instalamos:

```
apt-get update
apt-get install w32codecs libdvdcss2
```

Ahora quitamos el repositorio que hemos añadido (ya no lo necesitamos) de /etc/apt/sources.lst y actualizamos la lista con los repositorios de antes únicamente.

```
apt-get update
```

Ya podemos abrir el 80% de los videos.