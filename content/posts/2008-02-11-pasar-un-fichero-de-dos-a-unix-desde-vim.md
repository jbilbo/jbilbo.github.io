---
title: 'Pasar un fichero de DOS a UNIX desde vim'
date: '2008-02-11'
tags:
- Software Libre
---

Es un search/replace para quitar todas las “^M” típicas de un fichero DOS.

```
:%s/Ctrl-V Ctrl-M/ /g
```

Falta puntualizar que pongo Ctrl-V + Ctrl-M para que no se haga
copy-paste. Esta combinación de teclas produce el “^M” necesario (el de
carry return).