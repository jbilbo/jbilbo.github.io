---
title: "Comportamiento de la rueda del ratón en Ubuntu Dapper"
date: 2006-03-30T18:18:00+02:00
draft: false
tags: ["linux", "ubuntu"]
---

Ha habido [un bug](https://launchpad.net/distros/ubuntu/+source/firefox/+bug/31827) en Dapper (ya está resuelto) que le ha pasado a un cierto número de usuarios (a mi en el portátil, por ejemplo) y tiene que ver con la rueda del ratón. Donde más se notaba era al utilizar Firefox, si movías el scroll vertical de una página muy rápido, Firefox capturaba un evento del ratón... si movías rápido la rueda hacia arriba equivalía a "Ir a la página anterior" de Firefox, y si movías hacia abajo "Ir a la página siguiente"... muy muy molesto.

Si te pasa, simplemente pon en la sección de mouse de fichero /etc/X11/xorg.conf lo siguiente:

```
Option          "ZAxisMapping" "4 5"
```

La zona del mouse se identifica por la sección, etc...

```
Section "InputDevice"
        Identifier      "Configured Mouse"
        Driver          "mouse"
```

O también reconfigurando las X se aplicará sola la opción, sólo que tendreis que contestar las típicas preguntas:

```
sudo dpkg-reconfigure xserver-xorg
```

Otra manera de arreglarlo (aunque sólo para Firefox), sería inhabilitar ese "evento" en el navegador. Para hacerlo, poner en la barra de navegación de Firefox lo siguiente:

```
about:config
```

Ahora buscamos el parámetro siguiente

```
mousewheel.horizscroll.withnokey.action
```

Y le asignamos el valor "0" (zero).
