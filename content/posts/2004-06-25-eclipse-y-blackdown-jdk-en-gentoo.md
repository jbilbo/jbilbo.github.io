---
title: eclipse y blackdown-jdk en Gentoo
date: '2004-06-25T10:01:00.000-07:00'
tags:
- Software Libre
---

Detecté un bug con el paquete eclipse-sdk-2.1.3-r3 y la kit jdk de java "blackdown 1.4.1" en Gentoo, y lo <a href="http://bugs.gentoo.org/show_bug.cgi?id=54320">postee</a>.<br/><br/>El desarrollador no lo puede reproducir, así que me pregunto si alguno de vosotros (usuarios de Gentoo) lo puede reproducir. Se trata simplemente de emerger eclipse-sdk y ver si al ejecutarlo ($ eclipse-2) peta o no. A ser posible probarlo con la blackdown-jdk que es con la que ocurre el error (no afecta a sun-jdk).<br/>Recuerdo que en Gentoo se pueden tener varias máquinas virtuales a la vez instaladas y elegir cuál utilizar por defecto con el script "java-config".<br/><br/>Si alguien lo prueba que me envie un mail comentándomelo, o si lo prefiere lo postee directamente en el bugzilla de gentoo.<br/><br/><b>Actualización</b>:<br/>Ahora soy yo quien tampoco puede reproducirlo... impresionante, no sé qué ha debido de cambiar... he estado emergiendo y desemergiendo el java y ahora no falla...