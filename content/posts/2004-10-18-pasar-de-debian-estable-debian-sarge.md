---
title: Pasar de Debian estable a Debian Sarge
date: '2004-10-18T13:49:00.000-07:00'
tags:
- Software Libre
---

Tengo un servidor (K5 a pocos MHz) con Debian en casa y voy a revivirlo un poco...

A día de hoy:

Woody es la rama stable de Debian.
Sarge es la rama testing de Debian.
Sid siempre será la rama unstable de Debian.

También hay que tener en cuenta que la rama stable siempre seguirá siendo la rama stable, al igual que testing o unstable. Con esto quiero decir que si tenemos configurado Debian para la rama estable... nos da igual que sea estable Woody o Sarge porque siempre estarás en la rama estable. En cambio si tenemos nuestros repositorios como woody o como sarge... siempre estaremos en woody o sarge. Ahora mismo, si pasamos a Sarge pasaremos a la rama testing y dentro de un tiempo estaremos en la rama estable automáticamente. Puede parecer lioso pero es un estructura fácil y limpia.

A mucha gente usuaria de Debian estable, dado el poco tiempo que falta para que Sarge pase a ser estable, le interesará pasar a Sarge ahora mismo por la cantidad de paquetes a la que puedes acceder y las versiones no tan anticuadas de Woody. Un ejemplo es mldonkey, si no quieres andar con backports tienes que pasar a Sarge donde ya existe un paquete de este servidor p2p.

Para pasar de estable (actualmente woody) a Sarge es muy fácil, basta con retocar la línea de tu /etc/apt/sources.list. Yo la tengo así:

```
deb http://http.us.debian.org/debian stable main contrib non-free
deb http://non-us.debian.org/debian-non-US stable/non-US main contrib non-free
deb http://security.debian.org/ stable/updates main contrib non-free
```

Lo he cambiado a:

```
deb http://http.us.debian.org/debian sarge main contrib non-free
deb http://non-us.debian.org/debian-non-US sarge/non-US main contrib non-free
deb http://security.debian.org/ sarge/updates main contrib non-free
```

Y seguidamente:

```
apt-get update
apt-get dist-upgrade
```

Como podeis observar, Sarge ya tiene repositorio propio de updates para parches de seguridad, otra razón para pasar a Sarge y dejar Woody.

Editado: [Artículo](http://www.gpltarragona.org/node/view/309) en gpltarragona.