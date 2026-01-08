---
title: emergetest
date: '2004-06-03T11:21:00.000-07:00'
tags:
- Software Libre
---

Como siempre voy poniendo por aquí y por allá "emergetest" y como este comando sólo existe en mi ordenador (y en el del [sergio](http://www.marblestation.com) xD), no se entera la gente. Voy a dedicar un post a esto y así referenciaré aquí cada vez que ponga el comando.

Explicación:

emergetest es un alias que he puesto en mi fichero **$HOME/.bash_profile**, de esta forma:

```
alias "emergetest"="ACCEPT_KEYWORDS="~x86" emerge"
```

Es decir, es lo mismo escribir:

```
emergetest
```

que escribir:

```
ACCEPT_KEYWORDS="~x86" emerge
```

Así, con el alias emergetest puedo acceder a la parte inestable (últimas versiones) del portage de Gentoo de forma muy fácil.
