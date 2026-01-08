---
title: Acelerar la carga de webs en Firefox
date: '2005-01-10T07:17:00.000-08:00'
tags:
- Software Libre
---

Yo sólo he probado la de desabilitar el ipv6:

Abrimos Firefox, ponemos about:config en la zona donde se ponen las direcciones web para acceder a la configuración interna del Firefox. Hay una zona para buscar opciones (Filter), allí ponemos ipv6 y nos saldrá esto:

```
network.dns.disableIPv6
```

3er botón del ratón, Modify, y cambiamos el valor a "true".

A parte de esto, también podemos modificar los siguientes valores para acelerar el Firefox, estan explicados en [esta página](http://www.polinux.upv.es/node/303) de poLinux y recomendado sólo a los usuarios de ADSL/Cable.