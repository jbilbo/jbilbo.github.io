---
title: 'Reemplazar enlaces simbólicos'
date: '2009-06-12'
tags:
- Linux
- Software Libre
---

Para enriquecer el ejemplo, creamos dos directorios:

```bash
$ mkdir soy-un-dir
$ mkdir soy-otro-dir
$ ls
soy-otro-dir  soy-un-dir
```

Para crear un enlace simbólico en linux, usaremos el siguiente comando

```bash
$ ln -s soy-un-dir soy-un-link
$ ls -l soy-un-link
lrwxrwxrwx 1 jbilbo jbilbo 10 2009-06-12 17:08 soy-un-link -> soy-un-dir
```

De esta manera soy-un-link apunta a soy-un-dir. Si quisiéramos hacer que soy-un-link apuntara ahora a soy-otro-dir, la manera más sencilla es la siguiente:

```bash
$ ln -sfn soy-otro-dir soy-un-link
$ ls -l soy-un-link
lrwxrwxrwx 1 jbilbo jbilbo 12 2009-06-12 17:09 soy-un-link -> soy-otro-dir
```

* -s hace que nuestro enlace sea simbólico
* -f fuerza a reemplazar el link previo
* -n hace que no "siga" el link y lo trate como otro archivo "normal", para poder reemplazarlo. Sólo es necesario cuando el destino actual del enlace simbólico que se quiere reemplazar es un directorio, en caso de no serlo no afecta, así que en los scripts ponerlo siempre por si acaso.
