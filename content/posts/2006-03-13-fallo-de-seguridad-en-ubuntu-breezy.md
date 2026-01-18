---
title: "Fallo de seguridad en Ubuntu Breezy"
date: 2006-03-13T03:32:00+01:00
draft: false
tags: ["linux", "ubuntu"]
---

Se ha descubierto un [fallo de seguridad](http://www.ubuntu.com/usn/usn-262-1) en Ubuntu (sólo para los que hayan instalado desde cero la Breezy, que es la 5.10). El log de instalación va guardando paso a paso las opciones que vamos seleccionando... guarda incluso el password de usuario en texto claro (!!), y claro como el usuario en una instalación por defecto tiene permisos de "sudo" es posible acceder a root desde él.

Para arreglarlo simplemente haced un:

```bash
sudo chmod 600 /var/log/installer/cdebconf/questions.dat
```

Así sólo tiene permiso de lectura de ese fichero el usuario root.

No hace falta decir que si en la máquina que administrais teneis algún otro usuario que no seais vosotros ha podido ver la contraseña y por tanto se debería cambiar. Como no hace falta decirlo no lo voy a hacer.

Menudo fallo de seguridad... el punto positivo es que [al instante de publicarse](http://www.ubuntuforums.org/showthread.php?t=143334) el fallo ya se conocía solución sencilla para arreglarlo, y que los binarios actualizados para todas las arquitecturas con comunicado oficial incluido han sido lanzados [a las 8 horas despues](https://launchpad.net/distros/ubuntu/+bug/34606) de conocerse el error... ¡un domingo por la tarde!

PD: También lo cuentan en menéame [[1](http://meneame.net/story.php?id=8830)] [[2](http://meneame.net/story.php?id=8856)]

PD2: [La explicación](http://www.ubuntuforums.org/showpost.php?p=818037&postcount=61) del mantenedor del sistema de instalación.

PD3: El [exploit](http://www.ubuntuforums.org/showpost.php?p=818304&postcount=74) en perl.
