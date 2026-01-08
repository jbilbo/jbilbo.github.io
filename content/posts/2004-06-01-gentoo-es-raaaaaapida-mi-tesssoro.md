---
title: Gentoo es ráaaaaapida… mi tesssoro
date: '2004-05-31T17:28:00.000-07:00'
tags:
- Software Libre
---

![Tira Gentoo](http://tira.escomposlinux.org/ecol-161.png)

Para eso está openoffice-bin :P

```
(00:30:53) snuez: sobra el comentario del final
(00:31:18) snuez: porque podía haber puesto cualquier paquete donde dice oppen-office
```

Es cierto, ¿y a quién usuario de Gentoo no le ha pasado esto de la tira alguna vez (con otro paquete)? xDDD

Y es que no existe [la distribución perfecta](http://www.marblestation.com/blog/index.php?p=44) (no, no es Debian :P). Por otra parte, la mejor baza de Gentoo no es la adaptación a tu CPU, sino su sistema de paquetes (portage-emerge) y su filosofía en cuanto a nuevas versiones (rama estable-inestable, y pronto rama seguridad que sólo actualiza fallos de seguridad).

PD: Para que no se note la bajada de rendimiento mientras se compila algo, mejor usar un kernel con los parches que Gentoo recopila (gentoo-sources o gentoo-dev-sources), lleva preemptive y no va como el caballo del malo xDD

**Actualización**: Sergio me comenta que hay otra posibilidad. Existe la opción "PORTAGE_NICENESS" en el fichero /etc/make.conf que lo que hace es bajar la prioridad del portage directamente contra más alto es el valor.
