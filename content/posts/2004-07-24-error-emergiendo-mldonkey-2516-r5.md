---
title: Error emergiendo mldonkey-2.5.16-r5
date: '2004-07-24T09:48:00.000-07:00'
tags:
- Software Libre
---

<pre>The files /usr/lib/ocaml/pervasives.cmi and /usr/lib/ocaml/lablgtk/gPack.cmi<br/>make inconsistent assumptions over interface Pervasives<br/>make: *** [src/gtk/configwin/configwin_types.cmx] Error 2<br/>make: *** Waiting for unfinished jobs....<br/> <br/>!!! ERROR: net-p2p/mldonkey-2.5.16-r5 failed.<br/>!!! Function src_compile, Line 50, Exitcode 2<br/>!!! (no error message)</pre><br/><br/>Se soluciona:<br/><br/><pre>emerge --oneshot lablgl<br/>emerge --oneshot lablgtk<br/>emerge net-p2p/mldonkey</pre>