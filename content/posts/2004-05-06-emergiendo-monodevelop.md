---
title: Emergiendo monodevelop
date: '2004-05-05T19:49:00.000-07:00'
tags:
- Software Libre
---

Me he puesto a emerger monodevelop:<br/><br/><pre><br/>emergetest monodevelop<br/></pre><br/><br/>*Nota: comando <a href="http://jhernandez.gpltarragona.org/blog/archives/000091.html">emergetest</a>.<br/><br/>Y me ha dado error gecko-sharp. Para ver el error, mirar este <a href="http://bugs.gentoo.org/show_bug.cgi?id=50147">bug</a>.<br/><br/>La solución es bien sencilla pero igual no se te ocurre de primeras. Se trata de quitar el viejo y poner el nuevo:<br/><br/><pre><br/>emerge -C gecko-sharp<br/>emergetest monodevelop<br/></pre><br/><br/>He puesto el bug porque debe de ser fallo del ebuild (o almenos que el mantainer tenga constancia del error).<br/>En todo caso, ya tengo monodevelop 0.3 instalado :)