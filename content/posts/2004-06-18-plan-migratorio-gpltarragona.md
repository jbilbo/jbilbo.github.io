---
title: Plan migratorio GPLtarragona
date: '2004-06-18T06:50:00.000-07:00'
tags:
- Software Libre
---

Se avecinan cambios en los servidores. Vamos a tirar los que tenemos y vamos a poner un cluster de G5's xDD
No, No, sólo hay que actualizar :-)

Primero de todo: Apache & Mysql. Hay que pasar de la 1.x -> 2.x y de la 3.x -> 4.x. Dificultad: Fácil. Probado en mi casa ;-)

Segundo: Drupal. De la versión 4.2  -> 4.4.1 (quizás a 4.4.2 que esta a punto de salir). Dificultad: xungo. Debería probarlo en mi casa.
La [migración de drupal](http://gilugsite.sourceforge.net/?q=node/view/206) comportará también [una serie de cambios](http://www.badopi.org/node/view/485) relacionados con el utf-8. Drupal maneja ahora todo con utf-8, así que tendremos que migrar la base de datos de iso-15 a utf-8. Aparte de eso, también [Apache](http://www.gpltarragona.org/node/view/185) tendrá que ponerse en modo utf-8 para que visualice bien los acentos y demás. Esto comportará más cambios, porque en GPLtarragona [tenemos](http://www.gpltarragona.org/wiki/pmwiki.php) [almacenadas](http://planet.gpltarragona.org/) [muchas](http://www.gpltarragona.org/cursos/) [páginas](http://cvsweb.gpltarragona.org/cgi-bin/cvsweb.cgi/) [estáticas](http://bugzilla.gpltarragona.org/) [a parte](http://www.gpltarragona.org/art/) [de](http://www.gpltarragona.org/~marble/) [la](http://www.gpltarragona.org/~jbilbo/) [principal](http://www.gpltarragona.org) (drupal). Esto supongo que dará quebraderos de cabeza y se veran mal acentos y símbolos en algunas páginas durante un breve periodo de tiempo. También por supuesto comportará que la web esté fuera de servicio por un tiempo, es inevitable.

Otra migración: Plan GPLURV -> GPLtarragona. Hay que hacer que el dominio viejo rediriga al nuevo, y arreglar las estadísticas de la web (ahora sólo cuenta las entradas por el dominio viejo). Las tenemos ocultas por culpa [del spam](http://www.gpltarragona.org/node/view/147). También hay que poner estadísticas al planet y anunciarlo de la manera más digna posible en la web principal (que esta como oculto... xD).

Despues de la migración tenía pensado unirnos a los demás lugs en [este](http://www.badopi.org/node/view/421) proyecto, al que le llamaremos desde aquí a ser posible, Metaslug (metaslug.gpltarragona.org), porque el planet ya lo tenemos ocupado. Ya hablaré con trukulo por el irc cuando acabe la migración de drupal.

Esto no entra dentro ya del plan migratorio, pero como parece un TODO... también tenemos que hacer la asamblea general (principios de Julio a determinar por el secretario en breve), y quedar antes de eso para tomar ya sea unas cervezitas, o Nesquiks, o colacao energy's... xDD