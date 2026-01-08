---
title: 'Vaciar un archivo en Linux'
date: '2007-01-14'
tags:
- Software Libre
---

Hace
tiempo me preguntaba si existía algún comando o “truquillo” made in
unix para vaciar un archivo. Esto es, por ejemplo, si tenemos un
archivo de log de 10 Mb, queremos seguir teniendo el archivo pero que
ocupe 0 Mb. Esto va bien para resetear archivos de log o en general
para scripts de administración de sistemas que hagamos.

Cuando me lo pregunté busqué información y encontré algunos truquillos
que tengo apuntados en un txt muy feo y que a continuación voy a poner
aquí por si es de utilidad a alguien más.

La situación es que tenemos el fichero “mail.log” y queremos borrar el contenido:

```
> mail.log
```

Otra manera, redirigiendo /dev/null:

```
 cat /dev/null > mail.log
```

O copiando el “fichero vacío” /dev/null encima del nuestro:

```
cp /dev/null mail.log
```

Y listos, las tres maneras son válidas, aunque la primera (redirigir
la salida de un comando null) es sólo válida para shells tipo Bourne
(bash o sh).