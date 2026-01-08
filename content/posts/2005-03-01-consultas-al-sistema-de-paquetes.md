---
title: Consultas al sistema de paquetes
date: '2005-03-01T11:29:00.000-08:00'
tags:
- Software Libre
---

Se puede hacer todo tipo de consultas, pero especificando una: Quiero saber a qué paquete pertenece un archivo de mi sistema.

En Gentoo había 2 formas de hacerlo (que yo supiera):

Con el programa equery, que esta dentro del paquete gentoolkit:

```
equery b ruta-a-archivo
```

Con el programa epm (pretende ser un clon de rpm pero para ebuilds):

```
epm -qf ruta-a-archivo
```

Para Ubuntu y Debian, esta consulta se puede hacer con dpkg:

```
dpkg -S ruta-a-archivo
```

Por ejemplo:

```
$ dpkg -S /usr/share/dotnet/mono/gtk-sharp/gtk-sharp.dll
libgtk-cil: /usr/share/dotnet/mono/gtk-sharp/gtk-sharp.dll
```

Significa que el archivo /usr/share/dotnet/mono/gtk-sharp/gtk-sharp.dll pertenece al paquete libgtk-cil.

**Actualización**: [YosWink](http://www.gentoo-es.org/blog/18) me ha avisado de que qpkg (el que hacía servir yo para eso en Gentoo) ha quedado [obsoleto](http://bugs.gentoo.org/show_bug.cgi?id=75802) y por lo tanto se desaconseja su utilización porque desaparecerá del Gentoolkit dentro de poco. En su lugar se utiliza equery, que también pertenece al Gentoolkit. Gracias por el aviso ;-)