---
title: 'Permisos de escritura en una partición Windows (FAT32)'
date: '2005-05-19'
tags:
- Software Libre
---

Muchas veces me he encontrado con esta pregunta y siempre acabo mirando el "man mount" para responderla. Que útil es el blog :-P 

Pongo aquí una línea de fstab de ejemplo:

```
/dev/hda2    /mnt/win2    vfat    defaults,gid=100,umask=0002    0    0
```

Notas de lo más importante:

- /dev/hda2 es la partición FAT32

- /mnt/win2 es el directorio de tu Linux donde quieres montar (llámale
“montar”… llámale “que salga”) la partición para listar los ficheros.

- vfat es el sistema de ficheros FAT32.

- defaults es la opción para que todo sea por defecto.

- gid=100 es la opción para que todos los ficheros tenga de grupo el
“users”, que en mi máquina es el 100. En la tuya puede ser otro… quizás
el 1000. Míralo en /etc/group.

- umask=0002 es para que tanto el propietario (root) como los del grupo
(users) tengan permisos de leer/escribir/ejecutar archivos en esa
partición. Los demás sólo leer.