---
title: Mod_mono disponible en Gentoo
date: '2004-05-22T11:56:00.000-07:00'
tags:
- Software Libre
---

Ya se puede emerger mod_mono 0.8 (la última ahora mismo es la 0.9) desde Gentoo.

mod_mono es un módulo para Apache (2.x) del servidor Xsp del [proyecto Mono](http://www.go-mono.com). Por ahora está como masked y versión de xsp es la 0.13.

El tema Mono en Gentoo parece que por fin se está espabilando, salen ebuilds más habitualmente que antes y ya con el mod_mono creo que están todos los aspectos cubiertos. Pero lo importante es que se vayan actualizando conforme al proyecto, y eso creo que lo veremos a partir de la próxima 1.0.

```
# emergetest -p mod_mono

These are the packages that I would merge, in order:

Calculating dependencies ...done!
[ebuild  N    ] dev-dotnet/xsp-0.13   228 kB
[ebuild  N    ] net-www/mod_mono-0.8  +apache2  304 kB

Total size of downloads: 533 kB
```

*Nota: comando [emergetest](/posts/2004-03-20-de-mysql-archivo/).*
