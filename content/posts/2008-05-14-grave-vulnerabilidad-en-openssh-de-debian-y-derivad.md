---
title: 'Grave vulnerabilidad en OpenSSH de Debian y derivados'
date: '2008-05-14'
tags:
- Software Libre
---

Se
trata de una vulnerabilidad en el generador de números aleatorios del
paquete OpenSSH que viene en algunas versiones de Debian y derivados
(incluido Ubuntu). A lo que afecta en la práctica es que las claves
generadas pueden ser débiles (con un patrón parecido) y por tanto sería
posible romperla con de un ataque por fuerza bruta… sin tener que estar
computando durante años.

Total, que toca actualizar el paquete de nuestra distribución y
regenerar vuestras claves si teneis y las haceis servir de
autentificación contra un servidor externo.

[Información completa de Ubuntu](http://www.ubuntu.com/usn/usn-612-2). Sólo afecta las versiones 7.04, 7.10 y 8.04

[Información adicional](http://wiki.debian.org/SSLkeys) en el wiki de Debian.