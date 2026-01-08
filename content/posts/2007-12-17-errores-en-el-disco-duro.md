---
title: Errores en el disco duro
date: '2007-12-17'
tags:
- Software Libre
---

Si has experimentado algún tipo de error en tu disco duro (datos corruptos) o simplemente sospechas que algo puede no ir bien, de vez en cuando un repaso al disco no viene mal. Aunque las distribuciones linux ya de por sí te hacen un fsck de vez en cuando, por lo que en general no hace falta llevar mantenimiento de disco duro por parte del usuario (como debe ser).

Aún así, yo utilizo unos comandos cuando quiero/intento arreglar/resucitar un disco duro y que por si a alguien le es de utilidad (no le gusta mirarse el man del fsck o el badblocks) lo voy a poner aquí.

Tomamos como premisas lo siguiente:

- He arrancado con un LiveCD, hago las operaciones como root en un terminal (y con las particiones de mi disco duro desmontadas)
- mi disco duro es /dev/sda
- mi sistema de ficheros linux es Ext3
- linux esta en la partición /dev/sda3 (todo, sin separar)

Ahora un repaso al sistema de ficheros y que arregle todos los errores que encuentre automáticamente.

```
fsck.ext3 -f -tt -v -y /dev/sda3
```

Ahora un repaso físico al disco duro en busca de sectores defectuosos. Lo buscaremos en todo el disco duro en vez de sólo en la partición linux. Si sólo quereis mirar los sectores de esa partición en concreto, hay una opción en el fsck para que lo llame por ti.

```
badblocks -s /dev/sda
```

**Actualización**: Sergio me apunta (thx!) a que hacer el badblocks desde fsck.ext3 además actualiza la lista de inodos para guardarte qué sectores estan defectuosos y no utilizarlos. Mucho mejor de esta manera, utilizando el comando badblocks únicamente te los lista pero no hace nada. Entonces sería:

```
fsck.ext3 -f -c -tt -v -y /dev/sda3
```

(Prefiero siempre el modo lectura antes que el escritura no destructiva :P)

Por último, nunca viene mal intentar optimizar el sistema de ficheros (optimizar suena bien). Fsck tiene una opción para eso (-D):

```
fsck.ext3 -f -tt -v -D -y /dev/sda3
```
