---
title: Tomboy en Gentoo
date: '2004-10-21T20:56:00.000-07:00'
tags:
- Software Libre
---

**Actualización2:** Ya esta en el portage. Ver [post](/posts/2004-10-29-tomboy-ya-en-el-portage/).

Como todavía [no se deciden](http://bugs.gentoo.org/show_bug.cgi?id=64554) a subir el ebuild de [Tomboy](http://www.beatniksoftware.com/tomboy/) al portage de Gentoo, voy a facilitarlo yo mismo empaquetado para quien quiera utilizarlo.

[tomboy-gentoo-0.2.2.tar.gz](http://jhernandez.gpltarragona.org/aplicaciones/tomboy/tomboy-gentoo-0.2.2.tar.gz)

Instrucciones:

En modo root:

```
cd /usr/local/portage
wget http://jhernandez.gpltarragona.org/aplicaciones/tomboy/tomboy-gentoo-0.2.2.tar.gz
tar -zxvf tomboy-gentoo-0.2.2.tar.gz
```

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

**Actualizado a 27-oct-2004**: por el cambio de x11-libs/gtk-sharp -> dev-dotnet/gtk-sharp.