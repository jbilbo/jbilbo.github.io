---
title: 'Mínima seguridad para tu MySQL'
date: '2008-08-08'
tags:
- Software Libre
---

Si
vas a poner en producción un servidor de MySQL te interesará este
pequeño truco. En Ubuntu, no sé si se incluye por defecto en todos los
paquetes de MySQL, existe un comando llamado
“mysql_secure_installation” que hará el trabajo sucio inicial por
nosotros.

Por ejemplo, si teneis la BD por defecto tal y como la trae el sistema podremos ver en los logs lo siguiente:

```
WARNING: mysql.user contains X root accounts without password!
```

Donde X es un número y depende de la instalación. No sólo no es
recomendado tener al usuario root de MySQL sin password (aunque sólo
esté disponible para localhost), sino que tampoco lo son:

 - Tener un usuario anonymous

 - Permitir accesso de usuario root remotamente

 - Tener la base de datos de pruebas “test” (por defecto viene incluida siempre)

De estas cosas se encarga solito el comando:

```
/usr/bin/mysql_secure_installation
```

Y tendría que ser el primer paso después de la instalación del paquete MySQL destinado para producción.