---
title: "Errores con el apt-get en Ubuntu"
date: 2005-09-28T12:44:00+02:00
tags: ["Software Libre", "Ubuntu", "Linux"]
---

Qué pesados son estos errores de apt-get:

```
Leyendo lista de paquetes... Hecho
W: GPG error: http://es.archive.ubuntu.com hoary-updates Release: The following signatures were invalid: BADSIG 40976EAF437D05B5 Ubuntu Archive Automatic Signing Key ftpmaster @ubuntu.com
W: Tal vez quiera ejecutar 'apt-get update' para corregir estos problemas/ftpmaster
```

Ocurren tanto con synaptics como con apt-get y se arreglan haciendo apt-get update (o su equivalente en otros gestores) hasta que ya no salen... ¿no hay alguna manera de evitar estos errores a los usuarios?

No es lógico ni usable para el usuario "darle a recargar en el update-notifier hasta que no salga".
