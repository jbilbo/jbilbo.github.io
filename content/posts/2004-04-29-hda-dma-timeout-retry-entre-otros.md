---
title: '"hda: DMA timeout retry" entre otros…'
date: '2004-04-29T09:04:00.000-07:00'
tags:
- Software Libre
---

Durante unos días al arrancar el ordenador se quedaba parado mientras ejecutaba el hdparm del inicio. En el log se podía apreciar el error:

```
hda: set_drive_speed_status: status=0x58 { DriveReady SeekComplete DataRequest }
hda: channel busy
hda: dma_timer_expiry: dma status == 0x20
hda: DMA timeout retry
hda: timeout waiting for DMA
```

La solución era la más fácil del mundo, no se me ha ocurrido hasta hoy (que me he puesto dispuesto a arreglarlo ;). El caso es que... da problemas el dma? pues se quita de los parámetros del hdparm.

Mis parámetros antes:

```
-d1c1m16k1u1X70
```

Ahora:

```
-c1m16k1u1X70
```

Y es que el DMA ya se activa (al menos a mí) por defecto en el arranque, por lo que el resultado es el mismo (sin el error, claro) :)
