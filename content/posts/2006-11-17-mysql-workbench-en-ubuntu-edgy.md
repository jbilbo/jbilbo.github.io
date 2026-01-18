---
title: "MySQL Workbench en Ubuntu Edgy"
date: 2006-11-17T00:44:00
tags: ["Software Libre", "Ubuntu", "MySQL"]
---

Nos bajamos toda la suite de herramientas de MySQL ([Gui Tools](http://dev.mysql.com/downloads/gui-tools/5.0.html)), la Generic x86 Linux TAR (bundled dependencies) en mi caso que no tengo un ordenador de 64bits.

Descomprimimos y ponemos en /opt:

```bash
tar -zxvf mysql-gui-tools-5.0r5-linux-i386.tar.gz
sudo mv mysql-gui-tools /opt/.
```

Ahora instalamos una dependencia:

```bash
apt-get install liblualib50
```

Y ejecutamos como usuario normal lo siguiente antes del programa:

```bash
cd /opt/mysql-gui-tools
unset LANG
unset LC_ALL
./mysql-workbench
```

Lo podemos añadir en el fichero /opt/mysql-gui-tools/mysql-workbench, despues de la linia #!/bin/bash:

```bash
#!/bin/sh

unset LANG
unset LC_ALL

PRG="$0"
```

~~Y funciona de maravilla (teniendo en cuenta que es una versión alpha y puede contener muchos bugs):~~

Aunque arranca bien, en esta versión es **inusable** por la cantidad de bugs importantes que posee. Aún le queda...
