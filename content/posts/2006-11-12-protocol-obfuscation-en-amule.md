---
title: 'Protocol obfuscation en Amule'
date: '2006-11-12'
tags:
- Software Libre
---

El otro día estaba yo buscando cosas legales en el Amule cuando me salió lo siguiente:
![Protocol obfuscation amule](/images/posts/protocol-obfuscation-amule.png)

Entonces busqué rápido a ver si Amule estaba al día y vi que ya estan implementando esta característica que Emule [introdujo hace un par de meses](http://www.p2pnet.net/story/9817) y ahora empiezan a utilizar los servidores (o SuperPeers), como por ejemplo DonkeyServer No1.

Esta es una característica desgraciadamente cada vez más necesitada, ya
que los ISP’s introducen reglas de filtrado que cuando detectan
paquetes que provienen de redes P2P los bajan de prioridad, o en el
peor de los casos lo bloquean indiscriminadamente.

Este tipo de “filtro” ha hecho que en paises como Brasil hayan estado
meses en que los usuarios de ese ISP veian como sus clientes P2P apenas
podian bajar nada. Ahora gracias a esta característica, que “esconde”
la estructura, es mucho más dificil identificar qué tipo de servicio
esta detrás de ese paquete y a primera estancia se identifica como
“datos aleatorios”. Su definición en inglés según [la web de Emule](http://www.emule-project.net/home/perl/help.cgi?l=1&rm=show_topic&topic_id=848) donde podeis encontrar más información es la siguiente:

*“Protocol Obfuscation is a feature which causes eMule to
obfuscate or “hide” its protocol when communicating with other clients
or servers. Without obfuscation, each eMule communication has a given
structure which can be easily recognized and identified as an eMule
packet by any observer. If this feature is turned on, the whole eMule
communication appears like random data on the first look and an
automatic identification is no longer easily possible.”*

Recordad que [Emule](http://www.emule-project.net/), aunque  sea un cliente sólo para Windows, es libre con licencia GPL, así que los desarrolladores de Amule [ya estan en ello](http://www.amule.org/amule/thread.php?postid=61196#post61196), examinando el código del protocol obfuscation y implementándolo.