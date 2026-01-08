---
title: Javascript para mostrar imágenes aleatorias
date: '2004-09-11T20:27:00.000-07:00'
tags:
- Tonteridas Mias
---

Tienes un numero determinado de imagenes: por ejemplo 7, que estan guardadas en la carpeta img. Y quieres mostrar una cada vez que entras en una página web concreta.
Así, cada vez que entras ves una diferente (o no, si da la casulidad de que sale la misma, porque es aleatorio).

Este script sencillo cubre esa necesidad de una forma muy simple, pudiendo adaptar el numero de imágenes fácilmente, con sólo añadir otra línea "this". Un ejemplo de uso lo podeis ver en mi [página principal](http://jhernandez.gpltarragona.org).

```javascript
<script language="javascript">
function VecImagenes()
{
  n=0;
  this[n++]="img/friends.jpg";
  this[n++]="img/friends2.jpg";
  this[n++]="img/yo.jpg";
  this[n++]="img/conmigueldeicaza.jpg";
  this[n++]="img/decumple.jpg";
  this[n++]="img/grupito.jpg";
  this[n++]="img/enhispalinux.jpg";
  this.N=n;
}
var Imagenes=new VecImagenes();
src= Imagenes[ Math.floor(Math.random() * Imagenes.N) ] ;
document.write("<img src="+src+" align=right>");
</script>
```

Por otra parte, hace unos días añadí categorías a mi blog para diferenciar los diferentes temas que suelo tratar. Actualmente estan así las cosas:

Cine (25)
Libros (4)
Software Libre (104)
Tonteridas Mias (44)
Videojuegos (6)