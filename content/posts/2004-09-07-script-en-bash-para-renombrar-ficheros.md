---
title: Script en Bash para renombrar ficheros
date: '2004-09-06T21:27:00.000-07:00'
tags:
- Software Libre
---

Como gthumb estable en Gentoo (v. 2.2.1) no soporta las extensiones .JPG (la versión inestable 2.4.2 sí las soporta ya), he hecho un pequeño script en bash para que me traduciese todo mi álbum de fotos recursivamente de *.JPG a *.jpg, y de paso también que me quite los espacios en blanco en los nombres.

Es un script muy sencillo, puede servir para aprender un poco de bash y es fácilmente retocable para otros propósitos (se podría decir que esta es la versión estable porque la he probado yo en un superdirectorio con todo mi album y me ha funcionado correctamente... las demás versiones son experimentales).

```bash
#!/bin/bash
# Programa en bash que renombra recursivamente todos los ficheros *.JPG
# a *.jpg y quita todos los espacios en blanco.
func_renombrar()
    {
    for Fichero in *
    do
        (
        if [ -d "$Fichero" ]; then
            cd "$Fichero"
            pwd
            func_renombrar
        fi
        )
	Extension=`echo $Fichero | gawk -F. '{print $2}'`
	if [ "$Extension" = "JPG" ]; then
		SinEspacios=`echo $Fichero | sed -s 's/\ //g'`;
		NuevoNombre=`echo $Fichero | gawk -F. '{print $1".jpg"}'`
		echo "$Fichero -> $NuevoNombre"
		mv "$Fichero" "$NuevoNombre"
	fi
 done
 }

func_renombrar
```

**Actualización**: [Sergi](http://www.xaolin.com/) me ha enviado el script retocado con algunas mejoras (no lo he probado todavía, pero se agradece el feedback), y es interesante:

*-si hay "." en medio del fichero, a parte del que precede a la extensión, lo trate bien
-sea generico (pasandole la vieja y nueva extension por parametros)
-y alguna cosa más pero que ya son manías mías de programar y que no tienen nada que ver con el caso :P*

**Actualización1.1** [Edgar](http://www.lapeig.com) me ha avisado de un bug en el script del sergi, te dejaba todas las fotos sin extensión. Simplemente se tenía que cambiar la línea 25 que ponía:
*mv "$Fichero" "$NuevoNombre"
por esta:
mv "$Fichero" "$NuevoNombre.$nuevaextension"*
Ya esta arreglado para quien se lo descargue ahora.
Descargar/ver [renamefiles](/files/renamefiles)

**Actualización2**: [Sergio](http://www.marblestation.com) me apunta a otra posible [solución](http://www.marblestation.com/blog/index.php?p=83).

Algunos links de información:

[Bash: Ejemplos](http://www.iespana.es/pacodebian/bash.html)
[Bash by example, part2](http://www-106.ibm.com/developerworks/library/l-bash2.html)