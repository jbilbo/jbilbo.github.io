---
title: Gnome 2.8 estable en Gentoo!
date: '2004-11-12T08:42:00.000-08:00'
tags:
- Software Libre
---

Justamente que hoy hablaba cuando pasaría... por fin Gnome 2.8 es estable en Gentoo!. Me he dado cuenta viendo el [packages.gentoo.org](http://packages.gentoo.org) y he actualizado el portage de mi Gentoo por chroot desde la Ubuntu para ver si era cierto... y lo es!

Mis predicciones esta vez no fueron del todo desacertadas, de primeras predije que sería estable [el día 4 de noviembre](/posts/2004-09-16-gnome-28/) y más tarde rehice la predicción diciendo [el 20 de noviembre](/posts/2004-10-09-gnome-28-inestable-en-gentoo/)... vale, ha sido el día 12 de noviembre...  pero si hacemos la media aritmética de las 2 predicciones: 4 + 20 / 2 = 12!... 12 de noviembre! No está mal xD

Pues nada, ya sabéis:

```
emerge --sync
emerge -auD world
```

Lo que no sé es que pasa si no usas udev... supongo que perderás funcionalidades o algo... mejor [migrar](http://forums.gentoo.org/viewtopic.php?t=210428) si utilizas devfsd.