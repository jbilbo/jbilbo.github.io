---
title: Sustituir cadenas en vim
date: '2004-11-16T05:53:00.000-08:00'
tags:
- Software Libre
---

Ayer tuve que sustituir en un archivo de 180 Mb abierto con vim lo siguiente:

```
|
|>From
```

por

```
|
|
|From
```

Incluyendo los espacios en blanco (**actualización: he marcado cada línea, para que se vea únicamente, con el carácter "|" al principio**), que no sabía hasta ahora cómo los trataba vim. El comando de buscar y reemplazar que hice servir fue:

```
:%s/\n\n>From/\r\rFrom/g
```

En vim los "\n" (para buscar) son los saltos de línea y para poner una línea en blanco cuando reemplazas se utiliza "\r". Si buscamos 2 saltos de línea seguidos equivale a 1 línea en blanco.Y si lo sustituimos por 2 "\r" (nuevas líneas) obtenemos 2 nuevas lineas en lugar de 1 (que teníamos antes). Lo demás es simplemente sustituir el ">From" por el "From".

El comando buscar/reemplazar normal para que lo haga en todo el texto es:

```
:%s/texto-para-buscar/texto-para-reemplazarlo/g
```