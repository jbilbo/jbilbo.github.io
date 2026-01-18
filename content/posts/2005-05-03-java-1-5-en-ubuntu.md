---
title: "Java 1.5 en Ubuntu"
date: 2005-05-03T04:07:00+02:00
tags: ["Software Libre"]
draft: false
---

A partir de la versión 2.3.x de Azureus se recomienda la versión 1.5 de Java por su mejor funcionamiento/optimización. Así que me he decidido a cambiar la 1.4.x que tenía... todo esta explicado en el [wiki de Ubuntu](http://www.ubuntulinux.org/wiki/Java15), muy fácil.

Iba a hacer la manera rápida de instalar (añadiendo el repositorio), pero he visto que son muy lentos (15kb/s de media y Java ocupa mucho :-P) así que al final lo he hecho de forma manual, que resumiendo sería:

- Ir a http://java.sun.com/j2se/1.5.0/download.jsp y bajarse el JDK 5.0 Update X (donde X es un número natural xD). Yo haré este ejemplo con el Update 3.
- Aceptar licencia (puedes no aceptarla, y después de ver que no puedes bajártelo entonces aceptarla... :-P)
- Bajarse la "Linux self-extracting file", que acaba en .bin: "jdk-1_5_0_03-linux-i586.bin, 46.51 MB"
- Y hacer estos últimos pasos para crear y instalar el .deb:

```bash
$ fakeroot make-jpkg jdk-1_5_0_03-linux-i586.bin
$ sudo dpkg -i sun-j2sdk1.5_1.5.0+update03_i386.deb
```

Luego puedes probar si funciona la instalación poniendo:

```bash
$ java -version
java version "1.5.0_03"
Java(TM) 2 Runtime Environment, Standard Edition (build 1.5.0_03-b07)
Java HotSpot(TM) Client VM (build 1.5.0_03-b07, mixed mode, sharing)
```
