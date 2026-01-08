---
title: Proyectando…
date: '2005-02-07T03:16:00.000-08:00'
tags:
- Tonteridas Mias
---

He vuelto a retomar el proyecto final de carrera para acabarlo en junio (hay que acabarlo en junio, hay que acabarlo en junio, hay que...).

El tema de mi proyecto es la implantación de [Compiere](http://www.compiere.org) (un ERP open source) en una empresa.

Ahora mismo los desarrolladores estan trabajando para hacerlo independiente de la base de datos, para así poder escoger BD libres/open source, ya que ahora mismo Oracle pesa y el proyecto de compatibilidad con PostgreSQL no salía a cuenta por algunas carencia de las BD que Compiere necesitaba (no me acuerdo exactamente cuales). Total que lo más óptimo era hacerlo totalmente independiente antes que reimplementar las partes que lo incompatibilizaba con PostgreSQL.

Pero en Diciembre hubo una novedad, y es la [compatibilidad con Compiere](http://daffodildb.com/daffodil-compiere.html) de una BD concreta: [DaffodilDB](http://www.daffodildb.com/). La compatibilidad se la curró la propia empresa y tiene un su web los parches correspondientes. Es una BD comercial que tiene una licencia especial que la hace **gratis** (que no libre, los ingleses se estan jartando de confusiones tendrían que admitir en su lenguaje "Libre" para poder distinguirlo del "Free" con significado "Gratis") para utilizarla con Compiere. Ahora en Febrero [ha salido](http://www.daffodildb.com/daffodilcompieresupport-news.html) la versión final con soporte oficial. No tengo más referencia de esta BD, si es buena o no en rendimiento comparada con la competencia.