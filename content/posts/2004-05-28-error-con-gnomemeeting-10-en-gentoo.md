---
title: Error con Gnomemeeting 1.0 en Gentoo
date: '2004-05-27T17:44:00.000-07:00'
tags:
- Software Libre
---

Al parecer hay un error en Gentoo al emerger Gnomemeeting 1.00 (recién salido a estable). El fallo esta entre la librería pwlib y el soporte ldap (Openldap). El error es éste:<br/><br/><pre>checking for PWLib version... 1.6.3<br/>checking for OpenLDAP support in PWLIB... no<br/>configure: error: Sorry but the PWLib version you are using doesn't support LDAP<br/> <br/>!!! ERROR: net-im/gnomemeeting-1.00 failed.<br/>!!! Function econf, Line 365, Exitcode 1<br/>!!! econf failed<br/></pre><br/><br/>La solución la podemos encontrar <a href="http://bugs.gentoo.org/show_bug.cgi?id=45016#c8">aquí</a> y se trata de recompilar openldap, pwlib y gnomemeeting.<br/><br/><pre>emerge --oneshot openldap pwlib gnomemeeting</pre><br/><br/>Nota: si no ponemos el --oneshot no pasa nada, es opcional, pero sin este parámetro el portage se cree que emergemos openldap y pwlib porque nos interesan como aplicaciones (las almacena en /var/cache/edb/world). Y no es cierto, para nosotros son sólo dependencias... ... ¿que no queda claro?<br/><br/><pre>man emerge</pre><br/><br/>xDD