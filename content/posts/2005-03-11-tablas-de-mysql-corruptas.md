---
title: Tablas de Mysql corruptas
date: '2005-03-10T17:52:00.000-08:00'
tags:
- Software Libre
---

En GPLTarragona nos ha pasado 2 veces con esta, y es que el disco duro nuestro "rasca" mucho... El error es del tipo:

```
*fatal error*: No puedo abrir archivo: 'accesslog.MYI'. (Error: 145)
query: INSERT INTO accesslog (url, hostname, uid, timestamp) values('',
'xxxxxxxxxxx', 0, 1110478239) in
*/var/www/gpltarragona.org/htdocs/includes/database.mysql.inc* on line
*97
```

Se arregla con:

```
#locate accesslog.MYI
/var/lib/mysql/drupal/accesslog.MYI
#myisamchk -o /var/lib/mysql/drupal/accesslog.MYI
- recovering (with keycache) MyISAM-table '/var/lib/mysql/drupal/accesslog.MYI'
Data records: 10845
Data records: 10842
```