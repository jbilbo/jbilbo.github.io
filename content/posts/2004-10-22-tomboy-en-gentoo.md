---
title: Tomboy en Gentoo
date: '2004-10-21T20:56:00.000-07:00'
tags:
- Software Libre
---

<b>Actualización2:</b> Ya esta en el portage. Ver <a href="http://jhernandez.gpltarragona.org/blog/archives/000225.html">post</a>.<br/><br/>Como todavía <a href="http://bugs.gentoo.org/show_bug.cgi?id=64554">no se deciden</a> a subir el ebuild de <a href="http://www.beatniksoftware.com/tomboy/">Tomboy</a> al portage de Gentoo, voy a facilitarlo yo mismo empaquetado para quien quiera utilizarlo.<br/><br/><a href="http://jhernandez.gpltarragona.org/aplicaciones/tomboy/tomboy-gentoo-0.2.2.tar.gz">tomboy-gentoo-0.2.2.tar.gz</a><br/><br/>Instrucciones:<br/><br/>En modo root:<br/><br/><pre>cd /usr/local/portage<br/>wget http://jhernandez.gpltarragona.org/aplicaciones/tomboy/tomboy-gentoo-0.2.2.tar.gz<br/>tar -zxvf tomboy-gentoo-0.2.2.tar.gz</pre><br/><br/>Si no tienes mono 1.0 o superior instalado:<br/><br/><pre>echo "dev-dotnet/mono ~x86" >> /etc/portage/package.keywords<br/>echo "dev-dotnet/gtk-sharp ~x86" >> /etc/portage/package.keywords</pre><br/><br/>Y por último:<br/><br/><pre>echo "app-misc/tomboy ~x86" >> /etc/portage/package.keywords<br/>emerge tomboy</pre><br/><br/><b>Actualizado a 27-oct-2004</b>: por el cambio de x11-libs/gtk-sharp -> dev-dotnet/gtk-sharp.