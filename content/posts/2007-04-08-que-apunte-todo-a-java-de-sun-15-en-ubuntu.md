---
title: 'Que apunte todo a Java de Sun 1.5… en Ubuntu'
date: '2007-04-08'
tags:
- Software Libre
---

En Ubuntu existen los “alternatives”, que podemos gestionar a través de:

```
# update-alternatives
```

para elegir, en caso que 2 librerías o programas hagan lo mismo,
entre uno u otro. Un claro ejemplo es entre elegir la versión Java de
Sun o la versión Java de GNU (gcj) para ejecutar nuestros programas.
Para cambiarlo, ponemos:

```
# update-alternatives --config java
```

Y nos da elegir por menú entre las soluciones de máquina virtual que
tengamos. Es muy pesado en algunos casos (como este mismo de la máquina
virtual Java) en que se tiene que definir cada binario por separado qué
versión utililzar (si la de GNU o la de Sun o las que tengamos…). Para
definir de golpe que la máquina virtual (todo lo que haga servir el
entorno de ejecución) por defecto sea la 1.5 de Sun:

```
update-java-alternatives --jre java-1.5.0-sun
```

Y para definir que todo el entorno de ejecución y las herramientas
de desarrollo (JRE y JDK, es decir, todo) vaya a la 1.5 de Sun:

```
update-java-alternatives --set java-1.5.0-sun
```