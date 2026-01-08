---
title: Eliminar ojos rojos con Gimp
date: '2005-01-17T16:49:00.000-08:00'
tags:
- Software Libre
---

Buen [artículo](http://www.usuarios.lycos.es/ciberespaciojoven/Ojos_Rojos.htm) con los pasos a seguir para eliminar los ojos rojos de las fotos digitales.

Pero mejor aún el [script](http://gimpguru.org/download/red-eye.scm) que contiene al final para automatizar el proceso.

Como dicen en la web, las instrucciones para usarlo es meterlo dentro de tu carpeta de gimp en ~/.gimp-XX/scripts donde XX es la versión de tu Gimp. Por ejemplo, en mi caso:

```
mv red-eye.scm ~/.gimp-2.0/scripts
```

Luego dentro de Gimp, en el menú Script-fu -> Selection saldrá Red Eye y Red Eye Desaturate. El segundo es por si no tienes el plugin de "Mezclador de Canales", pero normalmente el Gimp ya lo incorpora.

El funcionamiento del script es tener seleccionado un trozito de ojo rojo, después seleccionar "Red Eye". Las parámetros por defecto deberían de bastar, si no va bien en el artículo ponen para qué es cada cosa.