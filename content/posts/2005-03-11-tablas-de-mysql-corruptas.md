---
title: Tablas de Mysql corruptas
date: '2005-03-10T17:52:00.000-08:00'
tags:
- Software Libre
---

En GPLTarragona nos ha pasado 2 veces con ésta, y es que el disco duro nuestro "rasca" mucho... El error es del tipo:<br/><br/><pre>*fatal error*: No puedo abrir archivo: 'accesslog.MYI'. (Error: 145) <br/>query: INSERT INTO accesslog (url, hostname, uid, timestamp) values('', <br/>'xxxxxxxxxxx', 0, 1110478239) in <br/>*/var/www/gpltarragona.org/htdocs/includes/database.mysql.inc* on line<br/>*97</pre><br/><br/>Se arregla con:<br/><br/><pre>#locate accesslog.MYI<br/>/var/lib/mysql/drupal/accesslog.MYI<br/>#myisamchk -o /var/lib/mysql/drupal/accesslog.MYI<br/>- recovering (with keycache) MyISAM-table '/var/lib/mysql/drupal/accesslog.MYI'<br/>Data records: 10845<br/>Data records: 10842</pre>