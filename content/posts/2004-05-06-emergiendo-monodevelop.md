---
title: Emergiendo monodevelop
date: '2004-05-05T19:49:00.000-07:00'
tags:
- Software Libre
---

Me he puesto a emerger monodevelop:

```
emergetest monodevelop
```

*Nota: comando [emergetest](/posts/2004-03-20-de-mysql-archivo/).*

Y me ha dado error gecko-sharp. Para ver el error, mirar este [bug](http://bugs.gentoo.org/show_bug.cgi?id=50147).

La solución es bien sencilla pero igual no se te ocurre de primeras. Se trata de quitar el viejo y poner el nuevo:

```
emerge -C gecko-sharp
emergetest monodevelop
```

He puesto el bug porque debe de ser fallo del ebuild (o al menos que el mantainer tenga constancia del error).

En todo caso, ya tengo monodevelop 0.3 instalado :)
