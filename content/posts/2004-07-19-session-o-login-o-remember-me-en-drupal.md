---
title: session o login o remember me en drupal, con apache2
date: '2004-07-19T12:54:00.000-07:00'
tags:
- Software Libre
---

Hasta ahora en gpltarragona.org, se tenía que hacer login cada vez que se cerraba el navegador. No aguantaba la sesión, y era muy molesto.
Al parecer he dado con la solución, y estaba delante mio todo el rato.

Vamos a la raiz (root) de nuestro directorio de drupal:

```
vi .htaccess
```

Vamos a la siguiente linea:

```
<IfModule mod_php4.c>
   # If you are using Apache 2, you have to use <IfModule sapi_apache2.c>
   # instead of <IfModule mod_php4.c>.
```

Lo dice muy claro en inglés, hay que cambiar el IfModule por:

```
<IfModule sapi_apache2.c>
```

Y ahora todo funciona bien.