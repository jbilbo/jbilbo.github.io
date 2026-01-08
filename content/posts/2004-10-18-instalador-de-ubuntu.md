---
title: Instalador de Ubuntu
date: '2004-10-17T20:40:00.000-07:00'
tags:
- Software Libre
---

He estado cerca de 1 mes sin ser [fashion](http://www.gpltarragona.org/node/view/296), no podía aguantarlo más!! Así que hoy he instalado Ubuntu Warty Warthog RC1 en el sobremesa... y antes de decir otra cosa... ¡Me cago en Ubuntu! Vale, puedo seguir.

Tenía las particiones de esta manera:

```
/dev/hda1 - NTFS WinXP
/dev/hda2 - FAT32
/dev/hda3 - reiserfs
/dev/hda5 - /boot reiserfs
/dev/hda6 - / ext3 Gentoo
/dev/hda7 - swap
/dev/hda8 - reiserfs
/dev/hda9 - reiserfs
```

Iba a borrar hda7 y hda8, para hacer más grande hda7 y meter Ubuntu en hda8. Aprovechando que ubuntu lleva un instalador con particionador, decidí que lo reparticionaría desde allí.

Hice los cambios dichos anteriormente en el particionador y todo pareció ir bien, el particionador me mostró lo que yo hice. En este cambio, sólo se veian afectados hda7 (ampliada) y hda8 (reducida). Luego decidí que hda8 fuese reiserfs... aún [sabiendo](http://www.marblestation.com/blog/index.php?p=198) que podía dar error en el gestor de arranque, pero pensé que al ser una nueva versión podría estar ya arreglado y que si fallaba me daba igual porque podía arrancar con el grub de Gentoo. El bug parece ser menos bug, porque da error en el momento de la instalación y no cuando arranca el grub... (algo es algo xD), pero... aún continuando la instalación sin gestor de arranque....... cuando reinicio ¡¡me doy cuenta de que no existe ninguna partición de las modificadas (hda7 y hda8) y me ha borrado hda9!! O_o

**Recomendación: Si podeis, no modifiqueis particiones desde el instalador (hacedlo desde otro linux o desde el liveCD de Gentoo por ejemplo) y elegir siempre de sistema de archivos el ext3.**

Después he reparticionado desde Gentoo y continuado la instalación con ext3. Ha ido todo bien, sólo he tenido que modificar el fichero de las X para cambiar la resolución (me la había puesto a 1600) y lo típico de personalizar la distro.

Otra cosa que no me ha gustado es que a la hora de instalar ciertos paquetes hay dificultades (léase mplayer, j2se-package... o java en general) que supongo que son cosa de no ser release oficial todavía, nada grave. Lo grave es que el particionador te "vuele" 3 particiones...