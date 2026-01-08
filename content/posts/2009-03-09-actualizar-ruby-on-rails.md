---
title: Actualizar Ruby on Rails
date: '2009-03-09'
tags:
- Developer
---

Antes de actualizar Ruby on Rails es conveniente actualizar también gems y asegurarnos que funciona bien con la versión de Ruby que tenemos instalada.

Después de esto:

```
gem install rails --include-dependencies
```

Para actualizar nuestros proyectos de Rails con las mejoras del nuevo rails, hacemos un:

```
cd /directorio/de/nuestro/proyecto
rake rails:update
```

Esto nos actualizará las funciones javascript, los scripts/ i archivos internos del framework como por ejemplo config/boot.rb.
