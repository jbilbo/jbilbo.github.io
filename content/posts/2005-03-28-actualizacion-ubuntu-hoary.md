---
title: Actualización a Ubuntu Hoary
date: '2005-03-28T12:35:00.000-08:00'
tags:
- Software Libre
---

Ya he actualizado 2 equipos de warty a hoary (ninguno de ellos el mio de casa... por ahora :P), y el resultado en los 2 (un servidor+escritorio y un escritorio) ha sido bueno.

Sólo me he encontrado con 1 problema, que los menus me salían medio castellano medio inglés (también lo vi en otro media catalan medio inglés). La solución es sencilla, Ubuntu tiene paquetes para los lenguajes por separado y sólo hay que instalarlos. Para castellano:

```
apt-get install language-pack-es
```

Para catalan:

```
apt-get install language-pack-ca
```

Ambos tienen como dependencia language-pack-base-xx donde xx es el código del país.

También para el firefox existe el paquete a parte: mozilla-firefox-locale-xx.

**Actualización 20:55**: Para instalar soporte en tu idioma de estas aplicaciones (mozilla, Openoffice, diccionarios...) sin preocuparte, existe el metapaquete language-support-xx. Así:

```
apt-get install language-support-es
```

Instalará esos paquetes en español. En este caso hay un bug (en catalan no), te baja el mozilla-firefox-locale-es-ar en vez del mozilla-firefox-locale-es-es que creo sería el adecuado, pero no creo que haya mucha diferencia.

**Actualización 01:14**: De hecho, instala tanto el es-ar como el es-es para que elijas el que prefieras. Así que no es ningún bug, ... como no ocupan casi nada no es problema.

En cuanto al paso a UTF-8 no es automático como pensaba, cuando inicias en el GDM puedes elegir o Spanish o Spanish (UTF-8). Si eliges este último y le dices que te lo ponga por defecto tu sistema pasará a ser UTF-8.

Ni dpkg-reconfigure locales ni nada...

**Actualización 23:56**: Al final he pasado a hoary en mi casa también :-D y al parecer sí que cambia automáticamente a UTF-8 según he visto al principio de la actualización:

```
(...)
Preconfiguring packages ...
Automatically selecting es_ES.UTF-8 locale in addition to es_ES.
(...)
Configurando locales (2.3.2.ds1-20ubuntu13) ...
Automatically selecting es_ES.UTF-8 locale in addition to es_ES.
Generating locales...
  es_ES.ISO-8859-1... done
  es_ES.UTF-8... done
Generation complete.
```

Pero igualmente he tenido que seleccionarlo en el GDM (Inicio de sesión) para que se me hiciera efectivo (es_ES.UTF-8), sino tenía sólo es_ES.