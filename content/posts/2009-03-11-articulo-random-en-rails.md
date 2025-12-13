---
title: Articulo random en Rails
date: '2009-03-11T13:45:00.000-07:00'
tags:
- Developer
---

Queremos obtener un registro aleatorio de la BD en Rails:<br /><br />def random<br />  @articulo = Articulo.find(:first, :order => 'RAND()')<br />end