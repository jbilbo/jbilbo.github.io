---
title: 'Actualizar a Dapper desde Breezy de manera fácil'
date: '2006-04-21T01:43:00+02:00'
tags:
- Software Libre
---

Han actualizado el paquete update-manager de Breezy para poder (si se quiere) actualizar a Dapper de manera fácil. Esta "feature" será importante y de interés general a partir del 1 de Junio, mientras tanto sólo le interesará a unos pocos, los que no les importe actualizar a una versión Beta. Desde hoy oficialmente Ubuntu es Beta, a poco más de 1 mes para salir.

Desde una terminal, basta hacer un:

```
gksudo "update-manager -d"
```

Para que en el actualizador de paquetes salga una opción para actualizar a Dapper. Si no he entendido mal, a partir del 1 de Junio ya no hará falta esa "-d" y saldrá la opción de "Actualizar" automáticamente porque la versión será estable y teóricamente según la [página del wiki de anuncio](https://wiki.ubuntu.com/DapperUpgrades) la -d es para tener la posibilidad de actualizar a versiones de desarrollo.

![Update Manager](/images/posts/update-manager-breezy.png)
