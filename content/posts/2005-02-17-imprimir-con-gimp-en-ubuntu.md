---
title: Imprimir con Gimp en Ubuntu
date: '2005-02-17T04:31:00.000-08:00'
tags:
- Software Libre
---

Hoy he tenido que imprimir con Gimp y no me funcionaba... extraño teniendo en cuenta que me funciona con cualquier otra aplicación.<br/><br/>La solución es, en el diálogo imprimir -> Configurar impresora : Quitar el parámetro -oraw.<br/><br/>Por ejemplo, yo lo tengo (con una HP Deskjet 3650):<br/><br/><pre>lp -s -dDeskJet-3650 -oraw</pre><br/><br/>Con lo que quedaría:<br/><br/><pre>lp -s -dDeskJet-3650</pre>