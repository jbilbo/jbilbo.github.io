---
title: emergetest
date: '2004-06-03T11:21:00.000-07:00'
tags:
- Software Libre
---

Como siempre voy poniendo por aquí y por allá "emergetest" y como este comando sólo existe en mi ordenador (y en el del <a href="http://www.marblestation.com">sergio</a> xD), no se entera la gente. Voy a dedicar un post a ésto y así referenciaré aquí cada vez que ponga el comando. <br/><br/>Explicación:<br/><br/>emergetest es un alias que he puesto en mi fichero <b>$HOME/.bash_profile</b>, de ésta forma:<br/><br/><pre>alias "emergetest"="ACCEPT_KEYWORDS="~x86" emerge"</pre><br/><br/>Es decir, es lo mismo escribir:<br/><br/><pre>emergetest</pre> <br/><br/>que escribir:<br/><br/><pre>ACCEPT_KEYWORDS="~x86" emerge</pre><br/><br/>Así, con el alias emergetest puedo acceder a la parte inestable (últimas versiones) del portage de Gentoo de forma muy fácil.