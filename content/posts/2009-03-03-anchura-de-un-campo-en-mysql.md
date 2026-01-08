---
title: 'Anchura de un campo en MySQL'
date: '2009-03-03'
tags:
- Developer
---

Si tienes en MySQL un campo de nombre "apellido" con tipo varchar(15) en la tabla "persona" y quieres obtener las personas que tienen un apellido más largo o igual que 8 carácteres… ¿cómo se hace en MySQL?

```sql
SELECT * FROM persona where LENGTH(apellido) >= 8
```

El comando clave es el LENGTH.
