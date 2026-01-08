---
title: Imprimir 4 transparencias en 1 hoja con OpenOffice
date: '2004-10-10T21:35:00.000-07:00'
tags:
- Software Libre
---

Hasta hoy no sabía hacerlo.

En el Openoffice -> Archivo -> Imprimir -> Imprimir a archivo.
In english: File -> Print -> Print to file.

Y ahora con las [pstools](http://gershwin.ens.fr/vdaniel/Doc-Locale/Outils-Gnu-Linux/PsUtils/):

```
psnup -l -m40 -4 transparencias.ps > transparencias-finales.ps
```

Por último lo paso a pdf:

```
ps2pdf13 transparencias-finales.ps transparencias-finales.pdf
```

Pero el resultado del pdf es un poco malo, las letras salen distorsionadas... a ver si encuentro alguna otra solución en esto.

**Actualización:** Aunque el resultado por pantalla del pdf sea malo, si lo imprimes sale perfecto. Y lo importante es justamente que lo imprima bien, porque para la visualización por pantalla se utiliza el fichero Openoffice no el pdf dividido en 4. Me queda hacer la prueba en windows, pero en linux con el acrobat propietario sale bien así que supongo que no debe de cambiar.

Me interesan estas cosas para los cursos de GNU/Linux de este año, a ver si podemos poner 4 transparencias/folio en la documentación. Y todo apunta a que sí podremos.

Editado: [Artículo](http://www.gpltarragona.org/node/view/308) en gpltarragona.