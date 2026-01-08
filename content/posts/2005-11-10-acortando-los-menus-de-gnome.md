---
title: 'Acortando los menus de Gnome'
date: '2005-11-10'
tags:
- Software Libre
---

Para la próxima versión de Ubuntu (dapper) y Gnome (2.14) los devs de Ubuntu tienen planeado [revisar los menus del actual Gnome y recortarlos](https://wiki.ubuntu.com/MenusRevisited)

Aunque todavía es un plan, hay un par de ideas que de verdad pienso que no son buenas…  [en los comentarios de la gente](https://wiki.ubuntu.com/MenusRevisited/Comments) la mayoría ya se comentan. Algunos:

*- If an item is primarily launched by a specific MIME type and works with one file at a time, it can be hidden*

Van a quitar el Totem del menu porque se ejecuta cuando hacemos clic en los videos… ¿?

*There should be a single point to access each function of the system*

¿Un sólo punto para acceder a un determinada función? Se trata de
facilitarle las tareas al usuario… lo que necesita en cada momento.
Inevitablemente algunos accesos se deben duplicar.

**New Login

- replace with button in gnome-screensaver

*New login nested window

- remove entirely

*Run as different user

- remove, not hide*

Matanza y desperdigación masiva de los ítems por doquier. Ole. Y
ponemos un botón en el salvapantallas y lo quitamos del menú. A esperar
10 minutos para poder darle…

Son sólo unos ejemplos, echadle un vistazo y opinad, esta todo lleno de “hide”.

También quieren ocultar del menu el bittorrent, xsane, image viewer,
preferencias de las ventanas… los primeros porque se ejecutan de otra
manera, haciendo clic por MIME o por otros programas (gimp->xsane) y
el último porque es para usuarios avanzados sólo, como el editor de
configuración, otro que ocultan.

Reflexionando sobre el desarrollo de Gnome, me da la sensación de
que los desarrolladores la mayor parte del tiempo la pasan
quitando/ocultando, o en su defecto cambiando de sitio funcionalidades
mientras que dejan de mejorar de forma relevante y impactante al
usuario.

Una vez Icaza diferenció la tarea de un desarrollador de Gnome con un
optimizador del Kernel, el primero cuando creaba una aplicación
producía un impacto mucho más grande al público que cuando el segundo
mejoraba la respuesta 1,14ms en una tarea determinada, lo cual tiene su
mérito y virtud pero de cara al público general no es relevante.

Los desarrolladores de Gnome cada vez se parecen más a los
optimizadores de kernel, en cuanto al impacto por supuesto, porque
tampoco noto mejoras de velocidad en la carga/respuesta de las
aplicaciones.