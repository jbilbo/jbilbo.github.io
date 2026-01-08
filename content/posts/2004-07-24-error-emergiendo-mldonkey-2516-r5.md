---
title: Error emergiendo mldonkey-2.5.16-r5
date: '2004-07-24T09:48:00.000-07:00'
tags:
- Software Libre
---

```
The files /usr/lib/ocaml/pervasives.cmi and /usr/lib/ocaml/lablgtk/gPack.cmi
make inconsistent assumptions over interface Pervasives
make: *** [src/gtk/configwin/configwin_types.cmx] Error 2
make: *** Waiting for unfinished jobs....

!!! ERROR: net-p2p/mldonkey-2.5.16-r5 failed.
!!! Function src_compile, Line 50, Exitcode 2
!!! (no error message)
```

Se soluciona:

```
emerge --oneshot lablgl
emerge --oneshot lablgtk
emerge net-p2p/mldonkey
```