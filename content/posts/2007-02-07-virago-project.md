---
title: 'Virago project'
date: '2007-02-07'
tags:
- Software Libre
---

Para
la asignatura de “Sistemas Informaticos I” hemos llevado a cabo una
práctica entre 4 compañeros y lo hemos montado todo como un proyecto de
software libre. La práctica consistía en una sistema de videovigilancia
(a través de webcams usb), y la hemos dividido en una parte servidor
que se encarga de las cámaras y una cliente (gráfico) que se conecta al
servidor para hacer toda la gestión.

Cada uno se ocupaba de una parte de la práctica: Base de dados, gestor de video, sistema de proxy y interfície cliente.

En cuanto a librerías y tecnología  utilizada, hemos hecho la parte de servidor (gestor de video, proxy y capa de BD) en [C++](http://es.wikipedia.org/wiki/C++) con las librerías [QT4](http://www.trolltech.com/products/qt/) (más el [motion](http://www.lavrsen.dk/twiki/bin/view/Motion/WebHome) para detectar movimiento y capturar video) y la parte cliente (interfície gráfica) en [Mono](http://www.mono-project.com/) (con C#) y [Gtk#](http://gtksharp.sourceforge.net/).

Yo me he encargado de la parte cliente, y aquí teneis una captura de cómo luce el producto final:
![Virago client](/images/posts/mainnotlogged.png)

Además, como muchos otros proyectos de software libre se puede bajar el código fuente y los binarios desde su [dirección web](http://virago.sourceforge.net/) o directamente la del [proyecto de sourceforge.net](http://virago.sourceforge.net/).

– [Download](http://sourceforge.net/project/showfiles.php?group_id=177352)