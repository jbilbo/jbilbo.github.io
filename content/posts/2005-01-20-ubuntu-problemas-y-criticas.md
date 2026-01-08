---
title: 'Ubuntu: problemas y críticas'
date: '2005-01-20T08:26:00.000-08:00'
tags:
- Software Libre
---

**Problemas**

Últimamente tengo algunos problemas en mi sistema. El primero de ellos se trata del rhythmbox, que no sé porque se queda congelado cada vez que lo ejecuto y le doy a reproducir una canción, no es aleatorio siempre pasa. No he localizado la fuente del error, incluso ejecutándolo en modo debug no detecto el fallo... quizá esté fuera, lo más seguro que con el driver de sonido.

**Actualización**: El problema era que no tenía el paquete gstreamer-mad, y el rhythmbox aunque lo necesita no lo tiene como dependencia.

Otro también tiene que ver con el sonido, y es que incomprensiblemente a veces se queda "mudo" el ordenador, vamos que el nivel de sonido interno de alsa se pone a zero... Es muy parecido a algo que [me pasó en Gentoo](/posts/2004-05-02-ya-tengo-alsa/). Es fácil de solucionar, con esto reinicializas los controles de volumen a su valor normal:

```
/etc/init.d/alsa stop
rm -f /var/lib/alsa/asound.state
/etc/init.d/alsa start
```

Por lo demás estoy muy contento con Ubuntu, sobretodo porque no me quita tiempo de administración. En Gentoo me pasaba demasiado tiempo pendiente de las actualizaciones/compilaciones y demás administración del sistema. Ahora no, te despreocupas y sólo te centras en lo importante, tú trabajo (o lo que estés haciendo xD).

**Críticas**

También quería hacer una crítica al estricto sistema de releases de 6 meses de Ubuntu. Me parece bien que cada 6 meses se pase a una nueva rama (Debian style), y que mientras tanto se resuelvan los fallos de seguridad de los paquetes estables. Pero hay un problema... ¿qué pasa con los paquetes con bugs? Warty es estable, pero el software tiene bugs lógicamente...

La respuesta es sencilla. Los bugs se solucionan... [para la siguiente release](https://bugzilla.ubuntu.com/show_bug.cgi?id=3374) (ejemplo puesto al azar), que se traduce en "a esperar 0<X<6 meses". Me parece una solución bastante mala la verdad... tener 3-4 meses un bug en un programa que usas a diario es inaguantable.

Otra solución sería instalar el paquete de Hoary (la versión inestable de Ubuntu). No la considero opción válida porque se quiere una distribución fácil de usar, apta para todos y tener medio sistema en hoary y con librerías de warty y... etc es a parte de peligroso sólo apto para gente con algo de experiencia.

Migrar por completo a Hoary es fácil, pero estareis de acuerdo conmigo que no sería la solución idónea... estaríamos ante el mismo problema que tiene Debian. Unos pocos usan su versión estable.

Yo creo que el sistema de releases esta bien. 6 meses con el mismo software es un período razonable. No me quejo de eso. Lo que sí me gustaría, es una política de actualización por bug según la dificultad que tendría añadir la corrección a warty, una estructura al fin y al cabo más flexible. No hay que ser tan estricto, si se descubre un bug en evolution o gaim, o cualquier aplicación, que es molesto o que puede afectar al rendimiento de los usuarios y corregirlo no comporte actualización de librerías masiva, ni nada por el estilo, se podría corregir.

Otra tontería es: "Uix... por 2 dias no ha entrado [Mono](http://www.go-mono.com) en Warty". Pues que lo metan 1 semana más tarde!, o cuando esté listo y testeado. ¿Por qué no? ¿No es serio? Yo lo veo más práctico y más útil por ejemplo que añadir paquetes de fotos de modelos cada mes como fondo de escritorio. No lo veo mal que se añadan esos, pero igualmente se podrían añadir otros que tengan listos o tenían intención de meter pero no dio tiempo.