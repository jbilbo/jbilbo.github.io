---
title: 'greph o grep sin hidden files (ficheros ocultos)'
date: '2008-02-22'
tags:
- Developer
- Software Libre
---

Grep es uno de los comandos de linux que más hago servir. Dentro de un proyecto normalmente busco las referencias a alguna palabra por grep recursivamente, pero lo malo es que si el proyecto tiene carpetas o archivos ocultos que no quieres incluir en la búsqueda (grep por defecto busca en todos los archivos, ocultos incluido) no hay manera fácil de hacerlo.

Por ejemplo, en el caso de que estes en un proyecto controlado por subversion y por tanto tienes muchas carpetas .svn con muchos .*, para ejecutar grep recursivamente pero sólo en ficheros y carpetas no ocultas deberíamos ejecutar esto:

```
grep -r "texto-a-buscar" `find \( ! -regex '.*/\..*' \) -type f`
```

No es un comando fácil para estar copiando/pegando en la consola… pero aquí entran los scripts en bash. Poniendo este sencillo script en cualquier lugar de vuestro path (/usr/local/bin por ej.) tendreis acceso a él desde cualquier usuario. Su uso es trivial, ponemos greph y luego el término a buscar. Ejemplos:

```
greph hola
greph 'hola que tal'
```

El código del script:

```bash
#!/bin/bash
if [ -z "$1" ]; then
  echo "Se necesita un parametro para buscar entre los ficheros (p.e. greph foo)"
else
  exec grep -r "$1" `find \( ! -regex '.*/\..*' \) -type f`
fi
```

PARA ASEGURAROS QUE NO HAY NINGÚN CARACTER RARO, EN VEZ DE COPIAR/PEGAR BAJARLO DESDE AQUÍ: **[greph](/scripts/greph)**

Acordaos de darle permisos de ejecución:

```
chmod +x greph
```
