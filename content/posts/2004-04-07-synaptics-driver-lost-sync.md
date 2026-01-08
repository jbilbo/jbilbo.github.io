---
title: Synaptics driver lost sync
date: '2004-04-06T21:21:00.000-07:00'
tags:
- Software Libre
---

Uix, qué error más feo me daba. Esto lo he arreglado antes de configurar el touchpad pero he preferido postearlo por si le pasa a alguien más.

El error que daba era que el ratón en ocasiones se volvía loco y se iba donde quería apretando todos los botones y liando una que no veas en el escritorio...

Pero en el lenguaje técnico de los logs era este el problema:

```
Apr  7 03:38:30 mordor psmouse.c: Wheel Mouse at isa0060/serio2/input0 lost synchronization, throwing 3 bytes away.
Apr  7 03:38:34 mordor Synaptics driver resynced.
Apr  7 03:38:35 mordor Synaptics driver lost sync at byte 4
Apr  7 03:38:35 mordor Synaptics driver lost sync at byte 1
Apr  7 03:38:35 mordor Synaptics driver resynced.
Apr  7 03:38:37 mordor Synaptics driver lost sync at byte 1
Apr  7 03:38:37 mordor Synaptics driver lost sync at byte 1
Apr  7 03:38:37 mordor Synaptics driver lost sync at byte 1
Apr  7 03:38:37 mordor Synaptics driver lost sync at byte 1
Apr  7 03:38:37 mordor Synaptics driver lost sync at byte 1
Apr  7 03:38:37 mordor Synaptics driver resynced.
Apr  7 03:38:39 mordor psmouse.c: Wheel Mouse at isa0060/serio2/input0 lost synchronization, throwing 3 bytes away.
```

Un error muy feo :)

**Se soluciona quitando el soporte APM en el kernel**.

Ahora tengo el ACPI y ya no me da el fallo, lo que pasa es que no pilla el estado de la batería y no me apaga automático... pero bueno, ya miraré a ver si puedo hacer algo.
