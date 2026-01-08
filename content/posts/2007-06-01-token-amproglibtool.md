---
title: 'Token AM_PROG_LIBTOOL'
date: '2007-06-01'
tags:
- Developer
---

Error:

```
autoconf
configure.in:8: error: possibly undefined macro: AM_PROG_LIBTOOL If this token and others are legitimate, please use m4_pattern_allow. See the Autoconf documentation.
make: *** [all] Error 1
*** Exited with status: 2 ***
```

Solución:

Tan fácil como

```
apt-get install libtool
```