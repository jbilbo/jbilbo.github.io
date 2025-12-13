---
title: Tomboy ya en el portage
date: '2004-10-29T08:09:00.000-07:00'
tags:
- Software Libre
---

La <a href="http://bugs.gentoo.org/show_bug.cgi?id=64554">petición</a> del ebuild.<br/>El <a href="http://packages.gentoo.org/packages/?category=app-misc;name=tomboy">paquete</a> en el portage.<br/><br/>Así que ahora instalarlo es más fácil.<br/><br/>Instrucciones:<br/><br/>En modo root:<br/><br/>Si no tienes mono 1.0 o superior instalado:<br/><br/><pre>echo "dev-dotnet/mono ~x86" >> /etc/portage/package.keywords<br/>echo "dev-dotnet/gtk-sharp ~x86" >> /etc/portage/package.keywords</pre><br/><br/>Y por último:<br/><br/><pre>echo "app-misc/tomboy ~x86" >> /etc/portage/package.keywords<br/>emerge tomboy</pre><br/><br/>También he actualizado el artículo de gpltarragona, que ahora esta en <a href="http://www.gpltarragona.org/queue">la cola</a>, así que como lo he modificado se tiene que votar desde 0 otra vez, sorry :P<br/><br/>Editado: <a href="http://www.gpltarragona.org/node/view/310">Artículo</a> en gpltarragona.