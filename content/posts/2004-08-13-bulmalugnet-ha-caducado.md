---
title: bulmalug.net ha caducado
date: '2004-08-13T09:08:00.000-07:00'
tags:
- Software Libre
---

El dominio bulmalug.net con el que me conecto con jabber ha caducado como se puede ver haciendo un whois:<br/><br/><pre>Record last updated 02-03-2003 07:46:24 AM<br/>Record expires on 08-11-2004<br/>Record created on 08-11-2001</pre><br/><br/>Así que no puedo conectar al jabber... he mirado si cambiando el servidor bulmalug.net a bulma.net (que sí existe y hay servidor jabber) funcionaba pero no ha sido así, da un "Error de Flujo" o "Stream Error". <br/><br/>Teóricamente bulmalug.net redirige a bulma.net pero igual si te registras como nombre@bulmalug.net luego no puedes conectarte como nombre@bulma.net, ese ha sido mi primer pensamiento pero desconocía la causa.<br/><a href="http://www.pipetree.com/jabber/jdp/x59.htm#JDP-CH-3-TAB-1">Ésto</a> me lo aclaró un poco, al parecer el nombre de servidor es imprescindible, no así la ip. Así que tiene fácil solución:<br/><br/>En nuestro linux, abrimos como root el fichero /etc/hosts y le ponemos:<br/><br/><pre>130.206.130.95 bulmalug.net bulmalug</pre><br/><br/>que es la ip de bulma.net. Ahora ya tengo jabber.