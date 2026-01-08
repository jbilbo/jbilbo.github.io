---
title: subversion
date: '2004-04-26T17:19:00.000-07:00'
tags:
- Software Libre
---

Ya ha salido la versión 1.01 a estable en el portage en Gentoo del gestor de versiones [subversion](http://subversion.tigris.org/), así que a partir de ahora le podré echar un vistazo (antes había conflictos en el portage con el autoconf, etc... y por eso estaba masked).

A ver si me acaba gustando más que [cvs](http://www.cvshome.org/)... :)

**Actualización:** Al parecer sigue habiendo problemas con el autoconf, subversion necesita las siguientes versiones para funcionar:

```
 >=sys-devel/autoconf-2.59
=sys-devel/autoconf-2.57*
```

Mientras que el autoconf estable en Gentoo ahora mismo es:

```
autoconf-2.58-r1
```

Así que no entiendo por qué lo han pasado a estable con esto... la solución más correcta sería actualizar las autoconf a la versión inestable del portage (2.59) para así poder seguir con los "-U" y que no esté el autoconf cambiando de versión en cada actualización.

**Actualización2:** Nada, ni siquiera actualizado a ">2.59" se deja... así que me he cansado y lo he quitado hasta que solucionen el asunto (tampoco iba a utilizarlo ya). Para el que lo quiera tener aún así es muy fácil, simplemente se emerge (emerge subversion), se actualiza (emerge -UD world) y se inyecta el autoconf viejo (emerge -i ...).
