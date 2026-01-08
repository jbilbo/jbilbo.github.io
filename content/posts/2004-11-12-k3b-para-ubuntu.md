---
title: K3b para Ubuntu
date: '2004-11-11T19:58:00.000-08:00'
tags:
- Software Libre
---

K3b es una de esas aplicaciones por las que instalas dependencias monstruosas como kdelibs, kcontrol, kdebase o qt... pero es que es una Killer-ap. Sin duda es el mejor grabador de CDs para Linux... lo "malo" es que esta integrado con KDE. Esta claro que es una pega bastante tonta si la miramos de forma objetiva, siempre buscando el instalarse los mínimos megas, pero esta claro que el software libre se divide en Gnome/KDE, y cualquiera de los 2 tiene que tener una alternativa a cualquier tipo de aplicación con sus librerías GTK/QT para que el look&feel de la aplicación sea el más integrado y bonito con el escritorio que sea posible.

Ubuntu se basa en Gnome, por lo que no veremos a K3b en la "main" almenos de aquí a mucho, por lo que hay que instalarselo desde el "universe".

He encontrado un [pequeño "How-to" en inglés](https://www.ubuntulinux.org/support/documentation/howto/helpcenterhowto.2004-10-05.2946111988) de cómo hacerlo, ya que la instalación directa no es suficiente para que funcione sin problemas.

Los pasos básicos en castellano serían:

Abrimos una terminal root (**No hacemos sudo!**): Aplicaciones -> Herramientas de Sistema -> Root Terminal

```
apt-get install kcontrol cdrdao k3b
k3bsetup
```

En el k3bsetup lo cambiais lo que creais necesario (yo no he cambiado nada).

Por último sólo queda añadir un pequeño icono donde se quiera (en el menú 3er botón del ratón -> Menú Completo -> Añadir un nuevo elemento a este menú o en el escritorio con 3er botón del ratón -> Crear Lanzador)

Y poniendo la información siguiente:

Nombre: K3b
Nombre genérico: (en blanco)
Comentario: Aplicación sofisticada para grabar CDs
Comando: gksudo /usr/bin/k3b
Como icono coger el de k3b, esta en la librería de iconos de gnome o en la carpeta del k3b.

Ya podeis ejecutar k3b desde este icono, nos preguntará contraseña porque lo ejecutamos en modo root.

Nota: **Es necesario ejecutarlo desde root (y no un sudo simple desde usuario)** porque sino se carga el archivo .ICEauthority cambiándole los permisos a root:root. Si os pasa, cambiad los permisos de ese archivo entrado en root desde donde podáis (modo monousuario/liveCD...) y poniendo:

```
chown tu-usuario:tu-usuario .ICEauthority
```

En mi caso:

```
chown jbilbo:jbilbo .ICEauthority
```