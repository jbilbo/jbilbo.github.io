---
title: Actualizar Ruby on Rails
date: '2009-03-09T13:11:00.000-07:00'
tags:
- Developer
---

Antes de actualizar Ruby on Rails es conveniente actualizar también gems y asegurarnos que funciona bien con la versión de Ruby que tenemos instalada.<br />Después de esto:<br /><br />gem install rails --include-dependencies<br /><br />Para actualizar nuestros proyectos de Rails con las mejoras del nuevo rails, hacemos un:<br /><br />cd /directorio/de/nuestro/proyecto<br />rake rails:update<br /><br />Esto nos actualizará las funciones javascript, los scripts/ i archivos internos del framework como por ejemplo config/boot.rb.