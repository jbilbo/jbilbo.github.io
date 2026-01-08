---
title: 'Sonido en el Firefox con Flash en Ubuntu Hoary'
date: '2005-05-11'
tags:
- Software Libre
---

Si no suena es por culpa de un bug, se soluciona con un link simbólico:

```
sudo ln -s /usr/lib/libesd.so.0 /usr/lib/libesd.so.1
```

Reiniciando el sistema funciona, pero supongo que simplimente cerrando/abriendo el navegador ya pillará los cambios.

Sacado de la [guía de problemas de sonido de hoary](http://www.ubuntulinux.org/wiki/SoundProblemsHoary).
