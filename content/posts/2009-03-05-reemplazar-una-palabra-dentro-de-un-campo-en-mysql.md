---
title: 'Reemplazar una palabra dentro de un campo en MySQL'
date: '2009-03-05'
tags:
- Developer
---

Si
queremos cambiar dentro del campo descripcion de la tabla casa todas
las palabras que dicen “benita” por “bonita”, se haría de la siguiente
manera:

```
UPDATE casa SET descripcion=REPLACE(descripcion,'benita','bonita')
```