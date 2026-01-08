---
title: 'Actualizar servidores con Ubuntu sin entorno gráfico'
date: '2007-09-13'
tags:
- Software Libre
---

A
partir de feisty han sacado soporte para terminal del “update-manager”,
el actualizador de versiones de Ubuntu. Aclarar que no se trata de
actualizaciones puntuales sino para pasar de una release oficial a otra
(de las que salen cada 6 meses).

Por ejemplo, para los que tenemos servidores con la versión Ubuntu
7.04 Feisty, bastará hacer lo siguiente para pasar a la siguiente
versión (llamada Gutsy y que ahora esta en fase alpha, así que esperad
a que salga oficialmente para hacerlo):

```
sudo apt-get install update-manager-core
sudo do-release-upgrade
```

Y ahora seguir las instrucciones. Easy, fast… and free.