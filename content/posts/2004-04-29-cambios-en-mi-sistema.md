---
title: Cambios en mi sistema
date: '2004-04-28T18:22:00.000-07:00'
tags:
- Software Libre
---

He pasado al kernel "gentoo-dev-sources", es el kernel de la rama 2.6.x que mantiene la gente de Gentoo (lleva parches como el bootsplash o el supermount). Aparte también noto una mejora de rendimiento mientras compilo paquetes, con mi anterior kernel (development-sources, 2.6.x oficial de kernel.org sin parches) notaba que al compilar se me ralentizaba todo el sistema.

El cambio de kernel lo quería también para probar supermount en mi sistema: supermount te permite acceder a los discos extraíbles (CDs, diskettes, DVDs...) de forma automática sin tener que montar/desmontar el dispositivo: Cuando metes el CD, se monta automáticamente y puedes acceder de forma directa (a lo windolin user), y cuando apretas "eject" el CD se desmonta también de forma automática.

He aquí el cambio de línea del /etc/fstab que sufre, por ej., mi grabadora:

Sin supermount:

```
/dev/cdrom	/mnt/cdrom	auto	ro,noauto,user,exec	0 0
```

Con supermount:

```
none	/mnt/cdrom	supermount	fs=auto,dev=/dev/cdrom,--,users	0 0
```
