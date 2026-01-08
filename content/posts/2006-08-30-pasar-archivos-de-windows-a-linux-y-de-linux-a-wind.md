---
title: 'Pasar archivos de Windows a Linux y de Linux a Windows'
date: '2006-08-30'
tags:
- Software Libre
---

Eran
viejos tiempos cuando para pasar un archivo de Linux a Windows o
viceversa se hacía a través de una partición FAT32. Cuando
particionabas el disco ya eras consciente que tenías que crear esa
“partición puente” que unía los 2 sistemas operativos.

Pero eso era antes, hoy en día se escribe y lee bien desde los 2
sistemas operativos para particiones con sistemas de archivos NTFS (en
el caso de Windows, que es el típico) y Ext3 (en el caso de Linux, que
también es el típico).

Para Windows, lo que tenemos que bajar es la aplicación FS-Driver:

[http://fs-driver.org/download.html](http://fs-driver.org/download.html)

Te permitirá integrar totalmente las particiones Ext2 y Ext3 de Linux como si fueran una de Windows.

Y para Linux, existe el driver ntfs-3g que comentó [Sergio](http://www.marblestation.com/blog/?p=585) y también se habló en [Barrapunto](http://barrapunto.com/article.pl?sid=06/08/23/1838250&mode=thread):

[Instalación en Ubuntu dapper](http://harrolf.blogspot.com/2006/08/linux-ntfs-conseguido-ntfs-3g.html) ([original en inglés](http://www.ubuntuforums.org/showthread.php?t=217009))

Que no he probado personalmente pero parece que funciona muy bien.

Entonces… ¿podemos enterrar ya las particiones FAT32? Nadie las echaría de menos creo yo… ¡viva los archivos de más de 4Gb!