---
title: I’m so happy!
date: '2004-07-03T05:53:00.000-07:00'
tags:
- Software Libre
---

Me han aceptado los dos ([1](http://bugs.gentoo.org/show_bug.cgi?id=55272) y [2](http://bugs.gentoo.org/show_bug.cgi?id=53724)) parches del k3b :-)

Esta puesto en el ebuild "k3b-0.11.12.ebuild", que ahora mismo es la versión inestable, así que si hacemos un:

```
emergetest -p k3b
```

Se instalará con ese ebuild. Changelog:

```
*k3b-0.11.12-r1 (03 Jul 2004)
  03 Jul 2004; Heinrich Wendel [lanius-arroba-gentoo.org] k3b-0.11.11.ebuild,
  k3b-0.11.12-r1.ebuild, k3b-0.11.12.ebuild, k3b-0.11.6.ebuild,
  k3b-0.11.9.ebuild:
  add icon for gnome, bug #55272, remove old versions, add arts useflag
```

**actualización 13:39**: También me han aceptado [el parche](http://bugs.gentoo.org/show_bug.cgi?id=55131) de knock!