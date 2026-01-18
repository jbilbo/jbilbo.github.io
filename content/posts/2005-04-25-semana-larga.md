---
title: "Semana larga"
date: 2005-04-25T22:36:00
tags: ["personal"]
draft: false
---

Se cayó el server, yo hecho un asquito en casa sin poder ir a ver qué le pasa... también estaba en medio de una faena en el proyecto final de carrera... en fin, semana K.O.
Hoy lunes por la tarde he podido ir a arreglar el servidor, éstos son los detalles:

Daba un error VFS: Unable to mount root partition al arrancar nada más llegar y arrancar/reiniciar (no parecía fallo de RAM).
Luego le he hecho un memtest porque apuntábamos a que era fallo de RAM y no ha dado error durante ~20 minutos y de repente peta el memtest con un error de cpu:

Unexpected interruption - Halting...
Y todo lleno de numeritos, el CS:xxxx y la pila. Información de depuración...

He puesto otro disco duro a ver... y funcionaba todo sin problemas. Pongo el principal como esclavo y funciona todo sin problemas. Aprovecho para hacer backup de los datos (gpltarragona esta a salvo :P). Pongo el principal otra vez como master (como estaba al principio) y funciona todo sin problemas...
He hecho un fsck y un badblocks al disco duro y todo ok.

Conjetura: mala conexión del cable IDE?? Hubiera apostado por fallo de CPU si no se hubiese arreglado de repente... Resumiendo: Ni idea.
