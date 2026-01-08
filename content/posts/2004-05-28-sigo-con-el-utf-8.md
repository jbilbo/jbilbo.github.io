---
title: Sigo con el utf-8
date: '2004-05-28T10:58:00.000-07:00'
tags:
- Software Libre
---

He arreglado el problema completamente (por ahora no encontrado ningún fallo) en la terminal pura. Lo he conseguido con el programa "unicode_start". Lo he añadido a mi .bash_profile:

```
#cosas utf-8
export LESSCHARSET="utf-8"
unicode_start &> /dev/null
```

Le he puesto un "&> /dev/null" porque en el gnome-terminal me da estos errores cada vez que abro una sesión:

```
KDSKBMODE: Operación no permitida
kbd_mode: error al establecer el modo de teclado
Keymap 0: Permission denied
Keymap 1: Permission denied
Keymap 2: Permission denied
KDSKBENT: Operation not permitted
loadkeys: could not deallocate keymap 3
putfont: KDFONTOP: Operación no permitida
```

Aunque se activa bien. Así tendremos la terminal (tanto pura como virtuales) a UTF-8, y en el menú de gnome-terminal donde se selecciona se puede ver como se marca automáticamente a UTF-8 con este comando :-)

Por lo menos parece que lo estoy consiguiendo parcialmente. Esto es bueno de cara a una posible migración de los servidores de gpltarragona a UTF-8 después de exámenes. Como se tendrá que migrar la base de datos con el upgrade del drupal, es posible que también por concordancia se migre el sistema entero... no lo sé, se tendrá que mirar.

Seguimos investigando. Si al final lo consigo intentaré recopilar todo y hacer una miniguía en [gpltarragona](http://www.gpltarragona.org).

PD: Se me olvidaba, UTF-8 support in Gentoo sucks! :P Ahí queda eso.

**Actualización**: Resolución final sobre utf-8, [aquí](/posts/2004-06-30-gplito2-y-acentos/) :-)
