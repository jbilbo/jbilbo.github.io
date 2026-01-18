---
title: "MySQL Administrator se cuelga"
date: 2006-03-27T02:52:00+02:00
draft: false
tags: ["linux"]
---

La estabilidad en Linux de la última versión de MySQL Administrator no es que sea muy buena la verdad, según los comentarios de la gente en foros/bug-reports la versión windows funciona bastante mejor. Ahora mismo la última versión windows es la 1.1.9 y la última para Linux es la 1.1.6, quizás eso tenga algo que ver... ¿se esta descuidando la versión Linux? Espero que no.

Lo útil de este post es que he encontrado en la [ficha del bug](http://bugs.mysql.com/bug.php?id=17879) la solución a los cuelgues:

```bash
$ export DEBUG_DONT_SPAWN_FETCHES=1
$ mysql-admin
```

Para los que esten en Dapper les irá bien. En Ubuntu Breezy no esta la última versión de MySQL Administrator, pero igualmente en esa versión existe otro bug en sección "User Administration", creo que no te permitía crear usuarios para acceder desde otro ordenador (host).
