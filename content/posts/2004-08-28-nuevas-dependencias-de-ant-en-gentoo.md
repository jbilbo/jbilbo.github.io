---
title: Nuevas dependencias de ant en Gentoo
date: '2004-08-28T10:34:00.000-07:00'
tags:
- Software Libre
---

La nueva versión estable de [ant](http://ant.apache.org/) en Gentoo (dev-java/ant-1.6.2-r3) tiene como PDEPEND, que creo que significa dependencia de paquete (RDEPEND es dependencia de ejecución y DEPEND de compilación) a ant-optional, que como su nombre significa, es un paquete opcional (almenos antes). Ahora es un paquete obligatorio que se instala con ant, que no sería una catástrofe si no fuera porque este paquete arrastra unos cuantos, véase la lista:

```
[ebuild  N    ] dev-java/bsh-2.0_beta1  +gnome -kde  0 kB
[ebuild  N    ] dev-java/log4j-1.2.8  -doc  0 kB
[ebuild  N    ] dev-java/avalon-logkit-bin-1.2.2  -doc  0 kB
[ebuild  N    ] dev-java/commons-logging-1.0.4  -doc +jikes -junit  98 kB
[ebuild  N    ] dev-java/xerces-2.6.2-r1  -doc  5,200 kB
[ebuild  N    ] dev-java/jython-bin-2.1-r4  -doc  0 kB
[ebuild  N    ] dev-java/oro-2.0.8  -doc +jikes  337 kB
[ebuild  N    ] dev-java/commons-net-1.2.2  -doc +jikes  174 kB
[ebuild  N    ] dev-java/rhino-1.5_rc5  -doc +jikes  1,505 kB
[ebuild  N    ] dev-java/jzlib-1.0.5  -doc +jikes  48 kB
[ebuild  N    ] dev-java/jsch-0.1.15  -doc +jikes  180 kB
[ebuild  N    ] dev-java/regexp-bin-1.3  -doc  0 kB
[ebuild  N    ] dev-java/bcel-5.1  -doc +jikes  12,338 kB
[ebuild  N    ] dev-java/xalan-2.5.2  -doc  5,603 kB
[ebuild  N    ] dev-java/antlr-2.7.3   1,316 kB
[ebuild  N    ] dev-java/commons-collections-3.1  -doc +jikes  1,110 kB
[ebuild  N    ] dev-java/commons-beanutils-1.6.1-r1  -doc +jikes -junit  144 kB
[ebuild  N    ] dev-java/junit-3.8.1   3 kB
[ebuild  N    ] dev-java/jdepend-2.6  -doc +jikes  0 kB
[ebuild  N    ] dev-java/ant-optional-1.6.2-r2  -javamail  6,134 kB
```

Yo no estoy dispuesto a instalar todo este circo de dependencias sólo para poder tener instalado jedit, es decir, para hacer funcionar a ant simplemente como un make para java, lo mínimo, no necesito más. De hecho, esto no es necesario y la razón de haber introducido esta dependencia es que la gente posteaba muchos bugs sobre ant y sus dependencias, posteaban bugs que en realidad no lo eran, sino que no sabía utilizar las USE flags de ant-optional para tener todo lo que necesitaban. La solución del desarrollador ha sido meterlo todo en el saco y así seguro que no hay problemas... cosa que va en contra de la filosofía de personalización de la distribución.

La solución mas sencilla es enmascarar la nueva versión de ant, para que no tenga esa dependencia y seguir con la anterior (que no tiene ningún fallo de seguridad ni nada malo) hasta que hagan algo con este asunto (ideas hay):

```
echo ">=dev-java/ant-1.6.2-r3" >> /etc/portage/package.mask
```

Se puede seguir este lio de dependencias en este [bug](http://bugs.gentoo.org/show_bug.cgi?id=41889). En [este](http://bugs.gentoo.org/show_bug.cgi?id=61986) también se habla. Mirad tb el [hilo](http://forums.gentoo.org/viewtopic.php?t=215341) en el foro.