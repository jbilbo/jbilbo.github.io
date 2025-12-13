---
title: rcconf no funciona en hoary
date: '2005-03-30T10:39:00.000-08:00'
tags:
- Software Libre
---

Si actualizais a hoary no hagais servir rcconf porque no maneja bien los links no sé porqué (no he investigado, ahora no tengo tiempo). En su lugar podeis hacer servir el update-rc.d de toda la vida:<br/><br/>Para quitar un servicio del arranque (por ejemplo apache2):<br/><br/><pre>update-rc.d -f apache2 remove</pre><br/><br/>Para añadirlo:<br/><br/><pre>update-rc.d apache2 defaults</pre>