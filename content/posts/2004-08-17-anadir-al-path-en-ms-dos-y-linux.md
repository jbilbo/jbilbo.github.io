---
title: Añadir al path en MS-DOS y Linux
date: '2004-08-17T10:36:00.000-07:00'
tags:
- Tonteridas Mias
---

Siempre se me olvida cómo se hace en MS-DOS, los pongo como recordatorio que google ya me mira con mala cara :P

En MS-DOS, quiero añadir C:\TC\BIN al path:

```
SET PATH=%PATH%;C:\TC\BIN
```

En Linux, quiero añadir /home/bin al path:

```
export PATH="$PATH:$HOME/bin"
```