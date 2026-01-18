---
title: "Nueva revisión de la GPL"
date: 2005-04-26T00:01:00
tags: ["software libre"]
draft: false
---

Hay una nueva revisión de la licencia GNU GPL, sólo es para cambiar la dirección de la FSF tal y cómo he leído en [un post](http://www.advogato.org/person/roozbeh/diary.html?start=21) del Planet Gnome. Aquí en inglés el comunicado:

```
The FSF is releasing a new version of the GPL!  Unfortunately, it's
not version 3 yet.  Instead, it's the third revision of version 2.  Like
the previous revision, it will differ only in that it will contain
FSF's new address.  This version will be available and effective on
Friday, April 29, 2005.

When you next get the chance, please go through your source code and
replace the old copy of the GPL with the new version.  Also, old
notices should be replaced with new ones.  The following shell command
will do this for you in a sloppy way; its results should be carefully
checked:

find . -type f -exec sed -ie 's/59 Temple Place, Suite 330/51 Franklin
Street, Fifth Floor/;s/02111-1307/02110-1301/;' {} ';'

We will also be releasing new revisions of the LGPL and the FDL.
```

Así que ya esta dicho... el find puede ser útil. La LGPL y la FDL irán detrás... y pronto se espera también la GNU GPL v3.
