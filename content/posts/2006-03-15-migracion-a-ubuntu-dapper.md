---
title: "Migración a Ubuntu Dapper"
date: 2006-03-15T03:03:00+01:00
draft: false
tags: ["linux", "ubuntu"]
---

He pasado a Dapper y he tenido algunos problemitas. Paso a comentar cómo actualizar y como resolverlos:

Primero actualizar (**¡atención!** dapper es la versión de desarrollo de Ubuntu, no apta para sistemas estables y gente inestable, fácilmente alterable o con poca paciencia). Ponemos en el /etc/apt/sources.list lo siguiente:

```
#Dapper
deb http://archive.ubuntu.com/ubuntu/ dapper main restricted universe multiverse
deb http://security.ubuntu.com/ubuntu/ dapper-security main restricted universe multiverse
deb http://archive.ubuntu.com/ubuntu/ dapper-updates main restricted universe multiverse
```

Quitar (o comentar con #) el resto de lineas del fichero.

A continuación:

```bash
sudo aptitude update
sudo aptitude dist-upgrade
```

Con esto, al acabar ya estaremos en dapper. Recomendado hacerlo fuera de Gnome/KDE porque queda feo que peten los applets etc...

El último paso es reiniciar.

Paso a comentar algunos errores.

**1.- Al primer arranque no funciona... ¡no arranca! El error:**

```
ALERT! /dev/hdaX does not exist, dropping to a shell
```

Arrancamos con la última opción (el kernel más viejo) en Recovery Mode (ese sí que nos deja). Al arrancar hacemos un "ls /boot" y nos fijamos en el kernel más nuevo. Por ejemplo:

```
vmlinuz-2.6.12-10-686
vmlinuz-2.6.12-9-686
vmlinuz-2.6.15-18-686
```

Nos fijamos en la versión más nueva: vmlinuz-**2.6.15-18-686** y reinstalamos el "linux-image" con esa versión:

```bash
aptitude reinstall linux-image-2.6.15-18-686
```

Y listos. Ahora reiniciamos y podemos arrancar. ¿Por qué? No me he parado a mirarlo, supongo que un bug... si alguien lo sabe que lo comente.

**2.- Impresora no va.**

Mmmm... raro. Para solucionarlo, borrarla y volverla a crear. En mi caso los drivers de la impresora (HP Deskjet 3650) no estaban en la sección HP sinó en la sección HP(HPLIP).

**3.- Gaim se vuelve loco**

Impresionante lo que me pasó con el Gaim... va y autoinvita a todos los contactos de todas las cuentas que tenía disponibles (tenía también la de mi primo y una antigua)... Un jaleo de invitaciones brutal.

Mirad un screenshot que hice:

{{< figure src="/images/posts/gaim-crazy.png" alt="Gaim goes crazy!" >}}

**4.- Comportamiento de Gthumb**

Gthumb ahora abre las imágenes y no te deja pasar adelante-atrás... un paso atrás, espero que lo arreglen. Ahora cuando abres una imágen tienes que hacer Alt+Fin para abrir el browser-mode y poder navegar por las imágenes... Lo ideal esta claro que es que cuando hagas doble click en una imágen esta se abrá en el gthumb y que si apretas AvPag y RePag vaya a la anterior o siguiente imágen respectivamente... y por eso mismo se ha abierto un [bug en el bugzilla de Gnome](http://bugzilla.gnome.org/show_bug.cgi?id=325557). (**Actualización 25/04/2006:** ¡Ya lo han arreglado!)

**5.- Versiones de Openoffice**

Se mezclan las versiones anteriores y la nueva. Simplemente borrar todos los paquetes que tengas instalado que comiencen por "openoffice.org2". Se puede hacer fácilmente desde el synaptic.

**Conclusión**

En términos generales me esta gustando esta nueva versión de Ubuntu, se nota que carga más rápido en el arranque y que el Openoffice también (han integrando el ooqstart). Muy bonito el nuevo theme naranja también... y por supuesto las nuevas versiones de programas también se agradecen :-P (Mono, Amule, Beagle, F-spot, K3b, Mail-notification, Tomboy, Evolution, Firefox 1.5.0.1...)

Buen upgrade.
