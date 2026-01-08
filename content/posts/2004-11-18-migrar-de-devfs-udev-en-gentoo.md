---
title: Migrar de Devfs a Udev en Gentoo
date: '2004-11-17T19:53:00.000-08:00'
tags:
- Software Libre
---

Udev es la nueva forma de gestionar el /dev en linux, nacido para sustituir el bastante desastroso devfs. Actualmente **es un requisito para Gnome 2.8**, ya que lo utiliza para gestionar los dispositivos.

Los usuarios de Gentoo han estado utilizando prácticamente desde que salió la distribución esa gestión a través de Devfs (en en kernel se le reconoce por "/dev file system support (OBSOLETE)"), así que ahora toca el cambio.

Existe 2 guías que hablan sobre la migración de devfs a udev:

- [Guía completa para migrar a un kernel 2.6 en Gentoo](http://www.gentoo.org/doc/en/migration-to-2.6.xml). (inglés).
- [Guía de Udev para Gentoo](http://www.gentoo.org/doc/en/udev-guide.xml). (inglés)

Yo voy a resumir los pasos a seguir que he hecho para que funcione, siguiendo estas guías:

[Migramos al nuevo hotplug](/posts/2004-11-18-actualizacion-del-hotplug-en-gentoo/) (Si es que todavía no lo hemos hecho)

```
emerge --sync
emerge udev
```

Vamos a nuestro kernel (recomiendo el último gentoo-dev-sources):

```
cd /usr/src/linux
make menuconfig
```

Opciones requeridas:

```
General setup --->
  [*] Support for hot-pluggable devices

File systems --->
  Pseudo filesystems --->
    [*] /proc file system support
    [*] Virtual memory file system support (former shm fs)
```

Opciones que debemos deshabilitar (la de la dev se puede dejar, pero para qué...):

```
File systems --->
  Pseudo Filesystems --->
    [ ] /dev file system support (OBSOLETE)
      [ ]   Automatically mount at boot
```

Ahora compilamos y modificamos el grub como siempre:

```
make && make modules_install
cp arch/i386/boot/bzImage /boot/kernel-con-udev
vi /boot/grub/grub.conf
```

Si utilizamos genkernel, hay una manera para compilar el kernel con las opciones necesarias para udev automáticamente utilizando este comando:

```
genkernel --udev --menuconfig --bootloader=grub all
```

La opción --menuconfig te abrirá el menú del kernel par retocar lo que se quiera antes de empezar a compilar con las opciones que el genkernel pone. También automáticamente te actualizará el grub... suena muy bien si hace lo que dice, pero no lo he probado :)

Editado: [Artículo](http://www.gpltarragona.org/node/view/321) en gpltarragona.