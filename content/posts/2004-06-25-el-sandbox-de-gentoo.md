---
title: El sandbox de Gentoo
date: '2004-06-25T06:29:00.000-07:00'
tags:
- Software Libre
---

Ayer [sergio](http://www.marblestation.com/blog/index.php?p=143) escribía sobre el sandbox. Un ejemplo de error me lo he encontrado hoy probando la versión inestable de [bloGTK](http://blogtk.sourceforge.net/):

```
ACCESS DENIED  unlink:    /usr/bin/BloGTK
rm: cannot remove `/usr/bin/BloGTK': Permission denied
make: *** [install] Error 1

!!! ERROR: net-misc/blogtk-0.9 failed.
!!! Function src_install, Line 28, Exitcode 2
!!! Unable to compile blogtk

--------------------------- ACCESS VIOLATION SUMMARY ---------------------------
LOG FILE = "/tmp/sandbox-net-misc_-_blogtk-0.9-28897.log"

unlink:    /usr/bin/BloGTK
--------------------------------------------------------------------------------
```

He tenido otros problemas con el sandbox algunas veces, pero siempre lo he solucionado desinstalando antes la versión vieja. Es decir:

```
emerge -C blogtk
emergetest blogtk
```