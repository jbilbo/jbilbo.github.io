---
title: Tomboy ya en el portage
date: '2004-10-29T08:09:00.000-07:00'
tags:
- Software Libre
---

La [petición](http://bugs.gentoo.org/show_bug.cgi?id=64554) del ebuild.
El [paquete](http://packages.gentoo.org/packages/?category=app-misc;name=tomboy) en el portage.

Así que ahora instalarlo es más fácil.

Instrucciones:

En modo root:

Si no tienes mono 1.0 o superior instalado:

```
echo "dev-dotnet/mono ~x86" >> /etc/portage/package.keywords
echo "dev-dotnet/gtk-sharp ~x86" >> /etc/portage/package.keywords
```

Y por último:

```
echo "app-misc/tomboy ~x86" >> /etc/portage/package.keywords
emerge tomboy
```

También he actualizado el artículo de gpltarragona, que ahora esta en [la cola](http://www.gpltarragona.org/queue), así que como lo he modificado se tiene que votar desde 0 otra vez, sorry :P

Editado: [Artículo](http://www.gpltarragona.org/node/view/310) en gpltarragona.