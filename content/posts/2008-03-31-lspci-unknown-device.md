---
title: 'lspci: Unknown device'
date: '2008-03-31'
tags:
- Software Libre
---

A
veces lspci no conoce tu dispositivo porque es muy nuevo o cuando se
hizo la release no estaba en su base de datos. Una manera fácil de
actualizarlo es con “update-pciids”:

```
lspci
...
01:00.0 VGA compatible controller: nVidia Corporation Unknown device 0611 (rev a2)
...
```

Actualizamos

```
sudo update-pciids
```

Y ahora:

```
lspci
...
01:00.0 VGA compatible controller: nVidia Corporation GeForce 8800 GT (rev a2)
...
```

Nos reconoce perfectamente el dispositivo.

Visto en [ubuntuforums](http://ubuntuforums.org/showthread.php?t=661800).