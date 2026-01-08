---
title: pyeximon en Gentoo
date: '2004-10-26T17:54:00.000-07:00'
tags:
- Software Libre
---

[pyeximon](http://pyeximon.sf.net) es una interfaz gráfica para Gnome al servidor de correo [exim](http://www.exim.org/), hace un tiempo lo comentó sergio en su [blog](http://www.marblestation.com/blog/index.php?p=216) pero yo ya lo conocía gracias a [Ubuntu](http://www.ubuntulinux.org), ya que estan relacionados. La empresa detrás de Ubuntu es [Canonical](http://www.canonical.com/), que esta impulsada económicamente por [Mark Shuttleworth](http://www.markshuttleworth.com/), que tiene unos [bounties](http://www.markshuttleworth.com/bounty.html) (recompensas de dinero por hacer software libre) en su web y uno de ellos es un "Gnome Exim Monitor" (que ya se ha realizado y es el pyeximon). De hecho ya hable de estas bounties [anteriormente](/posts/2004-10-07-transparencias-de-la-conferencia-y/).

El caso es que he puesto en el bugzilla de Gentoo una [petición](http://bugs.gentoo.org/show_bug.cgi?id=68905) para que se incluya un ebuild en el portage de este software y parece que hay gente que se ha interesado por el tema. A ver si podemos hacer un emerge pyeximon en breve.

**Actualización** 27-oct-2004 - 01:15: Parece increíble... pero ya esta disponible el ebuild en el CVS!! que rápidos! :-) genial!
Ahora mismo todavía no esta sincronizado, pero cuando leáis esto seguro que ya sí. Como estará masked durante el tiempo de testeo, para probarlo deberéis hacer:

```
emerge --sync
echo "dev-python/rtgraph ~x86" >> /etc/portage/package.keywords
echo "net-mail/pyeximon ~amd64" >> /etc/portage/package.keywords
emerge pyeximon
```

*Atención. Por ahora [sólo esta](http://packages.gentoo.org/packages/?category=net-mail;name=pyeximon) para arquitectura amd64 (le acabo de decir que si puede añadir la x86 porque funciona perfectamente), mientras tanto como chapucilla he puesto arriba que meta en el package.keywords la ~amd64 como podeis ver, cuando esté para ~x86 se cambia ~amd64 por ~x86 en el fichero y listos.