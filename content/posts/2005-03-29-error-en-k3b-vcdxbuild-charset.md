---
title: 'Error en k3b - vcdxbuild: charset conversion failed'
date: '2005-03-29T10:34:00.000-08:00'
tags:
- Software Libre
---

Ocurre cuando intentas crear un videoCD desde un archivo mpg (MPEG1 O MPEG2). Es el primer problema que me he encontrado en Ubuntu relacionado con UTF-8. La solución la he encontrado en una [web alemana](http://www.ubuntuusers.de/wiki/multimedia:foto-video-cds_erstellen) donde hay una captura muy esclarecedora (**Actualización:** he quitado el enlace a la captura de la web alemana porque estaba caído su servidor, así que he hecho yo un screenshot de cosecha propia)

Este bug esta relacionado con el vcdimager que es el el nombre del paquete que lleva dentro la aplicación vcdxbuild, y como este paquete no esta en el main supongo que el arreglo del bug no es tan rápido (ni tampoco se puede reportar en el bugzilla de Ubuntu). Por suerte, así se arregla:

![Solución error k3b Ubuntu](/images/posts/k3b-vcdxbuild-ubuntu-peq.png)

Es decir, poniendo como parámetro de usuario para vcdxbuild:

```
--filename-encoding=iso8859-1
```

Lo he probado personalmente y funciona.