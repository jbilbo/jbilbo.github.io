---
title: Traducción actualizada de Monodevelop al español
date: '2004-07-26T11:18:00.000-07:00'
tags:
- Software Libre
---

Hoy he trabajado con Monodevelop y he visto que la mitad o más estaba sin traducir, puesto que desde la última traducción habían cambiado muchas cosas y añadido otras cuantas... así que me he puesto manos a la obra y la he actualizado (acabo de mandar el link a la lista):

source: [es.po](http://jhernandez.gpltarragona.org/aplicaciones/monodevelop/es.po)
binario: [es.gmo](http://jhernandez.gpltarragona.org/aplicaciones/monodevelop/es.gmo)

**Actualizado: He vuelto a actualizar la traducción haciéndolo con gettext 0.14.1, puesto que con el anterior (0.12) daba problemas. Mirad [este](/posts/2004-07-30-traduccion-final-para-monodevelop-06/) post.**

Ahora animo a que quien quiera echar una mano... que sepa que **todavía no existe traducción al catalán para monodevelop!**  A ver si alguien de gpltarragona la hace!
Si alguien está interesado en hacer la traducción, que utilice gtranslator 1.02 (usuarios de Gentoo, mirar [este bug](http://bugs.gentoo.org/show_bug.cgi?id=55332)) o Ktranslator y siga las instrucciones del README que hay en la versión subversion de Monodevelop, en el subdirectorio po/.
Para bajarse Monodevelop versión subversion:

```
svn co svn://www.monodevelop.com/svn/monodevelop/trunk/MonoDevelop
```