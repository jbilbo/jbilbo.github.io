---
title: Del portage
date: '2004-04-02T08:12:00.000-08:00'
tags:
- Software Libre
---

Hoy ha entrado en el portage monodevelop (masked, rama inestable), en su nueva versión 0.2. Se había demorado porque todavía no había paquetes para sus dependencias y es que en mono todavía se tira mucho de cvs. Por ejemplo no tiene soporte cairo a falta de una versión de este paquete, y la política de Gentoo es no dar soporte hasta que haya un release oficial del paquete (se niegan a hacer desde cvs, por eso la versión de mono estable es la 0.28 todavía).

Cuestión de tiempo, antes tampoco había versión de gtkmozembed-sharp (gecko-sharp) ni gtksourceview-sharp... (y ahora la hay) además también ha vuelto a entrar monodebugger (0.6).

```
valinor ~ # emergetest -p monodevelop

These are the packages that I would merge, in order:

Calculating dependencies ...done!
[ebuild  N    ] dev-libs/icu-2.8   0 kB
[ebuild  N    ] dev-dotnet/mono-0.31  +nptl  18,198 kB
[ebuild  N    ] x11-libs/gtk-sharp-0.18  +gnome -gnomedb +gtkhtml -libgda  1,287 kB
[ebuild  N    ] dev-dotnet/gecko-sharp-0.1   90 kB
[ebuild  N    ] dev-util/monodoc-0.13   3,942 kB
[ebuild  N    ] dev-dotnet/gtksourceview-sharp-0.1.0   276 kB
[ebuild  N    ] dev-util/mono-debugger-0.6   1,234 kB
[ebuild  N    ] dev-util/monodevelop-0.2  +nptl  2,280 kB

Total size of downloads: 27,309 kB

valinor ~ #
```

*Nota: comando [emergetest](/posts/2004-06-03-emergetest/).*

A parte, todavía no hay versión 2.6 de Gnome en el portage. Bueno sí la hay pero está "hard-masked", es decir no tienen acceso a ella ni los de la rama inestable (sólo para desarrolladores o gente muy lanzada xD).

Hay un rumor sobre esto: Se dice que los desarrolladores de Gentoo se están asegurando personalmente de que no ocurrió nada en la intrusión que hubo en los servidores de Gnome. Yo creo que simplemente lo están testeando y si no pasa a estable este fin de semana, apuesto por que lo hará el lunes día 5 de abril a la vez que el [boletín semanal](http://www.gentoo.org/news/en/gwn/gwn.xml).

Por cierto, el ebuild de gnome 2.6 del portage tiene como nombre 2.6_rc5, pero en realidad no es ninguna release candidate... supongo que le cambiarán el nombre en breve.