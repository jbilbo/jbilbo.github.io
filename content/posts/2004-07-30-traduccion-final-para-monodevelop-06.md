---
title: Traducción final para Monodevelop 0.6
date: '2004-07-30T10:34:00.000-07:00'
tags:
- Software Libre
---

He terminado la traducción de Monodevelop, he tenido que actualizarla desde la última vez porque lo hice con una versión de gettext antigua (0.12) y no cogía las traducciones de los archivos de código fuente *.cs, sólo de los xml y los de glade. [Este](http://lists.ximian.com/archives/public/monodevelop-list/2004-July/001116.html) mail de Todd Berman me lo aclaró.

Una vez arreglado, he sustituido las anterior traducción por esta nueva en el sitio de descarga, que he probado y funciona perfectamente:

source: [es.po](http://jhernandez.gpltarragona.org/aplicaciones/monodevelop/es.po)
binario: [es.gmo](http://jhernandez.gpltarragona.org/aplicaciones/monodevelop/es.gmo)

¿Nadie se atreve con la de catalán? Venga... teniendo la de castellano al lado es más fácil ;-)

PD: Para tener gettext 0.14.1 en Gentoo, basta con renombrar el ebuild de la 0.12-r1 a 0.14.1 y crear el digest. Después instala perfectamente (en x86 almenos).