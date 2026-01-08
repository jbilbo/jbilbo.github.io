---
title: "¿Por qué no elegir QT como librería?"
date: '2004-08-13T11:38:00.000-07:00'
tags:
- Software Libre
---

El proyecto KDE, gracias a un acuerdo con Trolltech en la licencia de la librería, jamás tendrá ningún problema con su "libertad" ni su continuidad... esta escrito para que así sea. Pero dejando de lado KDE si yo quiero hacer una aplicación (se supone que libre, no entro en decisiones de empresa), ¿debo tener en cuenta las librerías QT?

La respuesta más conservadora sería: Depende. Pero yo especificaría más la respuesta, en mi opinión a no ser que la herramienta sea una utilidad específica para KDE, las librerías QT no son una elección a considerar. Y la razón es que la licencia libre de las QT te prohíbe que tu aplicación sea multiplataforma sin tener que comprar una licencia a Trolltech. ~~Hay una [leyenda](http://barrapunto.com/comments.pl?sid=43461&op=&threshold=0&commentsort=0&mode=thread&pid=334250#334416) que dice que mientras tu programa sea libre... no tienes que pagar nada. Esto es falso. Si la plataforma de destino es Windows, esto no vale. Si quieres que tu programa libre corra bajo Windows, tendrás que pasar por caja~~.

Como dice [este](http://barrapunto.com/comments.pl?sid=43461&op=&threshold=0&commentsort=0&mode=thread&pid=334416#334434) mensaje en barrapunto de rvr:

*[Qt Edition Free Licensing](http://www.trolltech.com/products/qt/freelicense.html): «The Qt Free Edition is available under two open-source licences: the GPL (GNU Public License), and the QPL (Q Public License). Both these licenses are suitable for the development of **Free Open Source Software for Linux, Unix, and Mac OS X**».*

No me parece mal la política de Trolltech, cada uno hace lo que quiere y licencia como quiere su librería, faltaría más. Pero tenerlo en cuenta a la hora de hacer una aplicación multiplataforma. Las libertades que ofrece GTK (y digo GTK por ser la competencia directa con las QT) no son las mismas que ofrece QT.

PD: Por ej. en el mismo thread que se comenta eso de las QT también se habla de [PSI](http://psi.affinix.com/), el cliente de jabber libre. Tiene versión de windows y utiliza las QT... ~~ahora mismo esta [incumpliendo](http://barrapunto.com/comments.pl?sid=43461&op=&threshold=0&commentsort=0&mode=thread&pid=334434#334543) la licencia! La versión windows esta [en manos](http://barrapunto.com/comments.pl?sid=43461&op=&threshold=0&commentsort=0&mode=thread&pid=334543#335939) de Trolltech... y su juicio :S~~

**Un [mensaje](https://listas.hispalinux.es/pipermail/gpltarragona/2004-August/002009.html) de Lluís Pàmies a la lista de GPLTarragona ha aclarado mucho las cosas**. Las QT para windows son comerciales, propietarias o como quieras llamarlas. Si tu aplicación es ["de escritorio"](http://www.trolltech.com/products/qt/licensing.html) no hace falta pagar nada, aunque si lo que quieres es que tu aplicación sea comercial sí tienes que pagar. Sin duda es mucho mejor así, y el negocio de Trolltech consiste en esto.

Con esto, si tienes un programa GPL renúncias a vender tu programa para windows, donde tendrá que ser gratuïto sino tendrías que pagar a Trolltech, mientras que sí puedes venderlo para Linux/Unix y MAC.

Aclarado esto, es tu elección elegir una u otra. Yo... después de todo, me quedo con los [Wxwidgets](http://www.wxwidgets.org/)... ala xD.