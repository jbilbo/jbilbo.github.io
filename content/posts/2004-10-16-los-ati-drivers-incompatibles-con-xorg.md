---
title: Los ati-drivers incompatibles con xorg-x11-6.8.0
date: '2004-10-16T10:14:00.000-07:00'
tags:
- Software Libre
---

Decía en el [anterior](/posts/2004-10-14-cursos-de-linux-y-tema-xorg/) post que íban bien con los drivers de ati, pero no es cierto. Como dependencia en Gentoo los drivers de ati no aceptan las X.Org 6.8 (los desarrolladores ya saben que no funcionan con ellas), por lo que al compilar los drivers se compiló la versión 6.7 de las X.Org y no me di cuenta que estaba probando las anteriores...

Hoy sí he probado X.Org 6.8 con los ati-drivers versión 3.14.1 y no funcionan ni a la de 3!!.
He tenido que reiniciar 2 veces por los 2 cuelgues que se ha metido el ordenador intentando acceder a las X (ni por ssh tiraba...). Total, como no quiero quedarme sin 3D, he tenido que enmascarar manualmente las X.Org 6.8. Haced como root:

```
echo ">=x11-base/xorg-x11-6.8.0" >> /etc/portage/package.mask
```

Tirón de orejas para ATI que sigue sin levantar cabeza con sus drivers.

Si quereis utilizar Linux para algo 3D y necesitais las últimas tarjetas y no os decidís por Nvidia o ATI... coged Nvidia. Lo dice un usuario de ATI y [mucha](http://forums.gentoo.org/viewtopic.php?t=230640) más gente.