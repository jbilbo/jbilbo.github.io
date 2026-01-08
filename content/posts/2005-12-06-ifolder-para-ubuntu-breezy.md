---
title: 'iFolder para Ubuntu Breezy'
date: '2005-12-06'
tags:
- Software Libre
---

[iFolder](http://www.ifolder.com/)
es una herramienta multiusuario para sincronizar carpetas desde
diversos ordenadores a través de red local o internet. También es
posible compartir carpetas entre usuarios.

![iFolder](/images/posts/ifolder.png)

Lo primero es crear un servidor de iFolder (si ya existe un servidor
y sólo quieres la parte cliente, pasa directamente al Paso 2), que
llamaremos SimpleServer, que almecenará todos nuestros archivos y se
encargará de gestionar la administración de cuentas, etc…

Se aconseja que el servidor de iFolder esté en un ordenador separado a
donde instalamos el cliente, pero hay gente que que lo ha probado desde
una misma máquina y le funciona.

**Paso 1**

```
sudo aptitude install libtool automake1.9 build-essential mono-devel intltool cvs
libxml2-dev libstdc++5 pkg-config mono checkinstall
```

Ahora bajamos los fuentes de Simias, el corazón de iFolder:

```
mkdir ~/simpleserver
cd ~/simpleserver
export CVS_RSH=ssh
cvs -z3 -d:ext:anonymous@forgecvs1.novell.com:/cvsroot/ifolder co simias
```

Os pedirá la contraseña, ponemos “anonymous”.

Ahora pasaremos a compilarlo

```
cd ~/simpleserver/simias
./autogen.sh --prefix=/usr/local/simias && make && sudo checkinstall
```

Crearemos un .deb para integrarlo en nuestro gestor de paquetes de
Ubuntu. En versión podeis poner la fecha en la que estais, por ej.
20051205. En nombre, descripción, comentario… etc, podeis poner
“simias” y listo. Es muy posible que dé error al instalar. Bien por un
carácter no válido en un campo de descripción del paquete o bien porque
al intentar instalar el .deb, intenta sobreescribir algún archivo que
ya existe (como el README del paquete autogen por ejemplo).

En caso de que pasará esto, se instala manualmente (el paquete .deb
habrá quedado guardado en el mismo directorio donde estamos). Bastaría
un:

```
dpkg -i --force-all simias*
```

Ahora a por el servidor SimpleServer:

```
cd other/SimpleServer
sudo make install-simpleserver
```

Listo, podemos configurarlo desde:

```
/usr/local/simias/etc/SimpleServer.xml
```

Por ejemplo:

```
<?xml version="1.0" encoding="utf-8" ?>
<domain Name="SimpleServer" Description="Brady's Simple Server">
        <member Name="jbilbo" Password="*****" Owner="true">
                <first>Jonathan</first>
                <last>Hernández</last>
        </member>
        <member Name="pep" Password="******">
                <first>Pepe</first>
                <last>Ermaschulo</last>
        </member>
</domain>
```

Y se puede arrancar desde el siguiente script:

```
/usr/local/simias/bin/simpleserver
```

También he creado un script para que se pueda ejecutar como demonio de arranque. Lo pondremos en /etc/init.d/ifolder:

```
#! /bin/sh
#

PATH=/bin:/usr/bin:/sbin:/usr/sbin
DAEMON=/usr/local/simias/bin/simpleserver

# Arguments to atd
#
ARGS=""

test -x $DAEMON || exit 0

. /lib/lsb/init-functions

case "$1" in
  start)
    log_begin_msg "Starting Novell iFolder..."
    start-stop-daemon --start --quiet --exec $DAEMON -- $ARGS
    log_end_msg $?
    ;;
  stop)
    log_begin_msg "Stopping Novell iFolder..."
    start-stop-daemon --stop --quiet --exec $DAEMON
    log_end_msg $?
    ;;
  force-reload|restart)
    sh $0 stop
    sh $0 start
    ;;
  *)
    log_success_msg "Usage: /etc/init.d/ifolder {start|stop|restart|force-reload}"
    exit 1
    ;;
esac

exit 0
```

Aunque no va fino a la hora de apagarlo nos servirá para encenderlo en el arranque. Lo añadimos a los runlevels por defecto:

```
update-rc.d ifolder defaults
```

Y la parte de servidor ya esta completa.

**Paso2**

Ahora necesitamos un cliente para conectarnos a ese servidor. En este caso podeis hacer servir los .deb que ya he creado yo:

[simias_2005.11.12-1_i386.deb](http://jhernandez.gpltarragona.org/aplicaciones/ifolder/simias_2005.11.12-1_i386.deb)

[ifolder_2005.11.12-1_i386.deb](http://jhernandez.gpltarragona.org/aplicaciones/ifolder/ifolder_2005.11.12-1_i386.deb)

Para instalar:

```
dpkg -i --force-all simias_2005.11.12-1_i386.deb
dpkg -i --force-all ifolder_2005.11.12-1_i386.deb
```

Si más adelante queremos desinstalar los paquetes que hemos creado, sería de esta manera:

```
dpkg -r ifolder simias
```

Estaría bien contar con el soporte de Nautilus, pero no he
conseguido compilarlo desde los fuentes… si alguien lo consigue que me
pase el .deb que lo colagaré aquí también.

Encontrareis el cliente para otras distribuciones (Suse, Fedora…) o Windows en la [sección de descargas](http://www.ifolder.com/index.php/Download) de la web de iFolder.

Más info:

- [Building SimpleServer](https://wiki.ubuntu.com/BuildingSimpleServer)

- [Buiding iFolder](https://wiki.ubuntu.com/Building_iFolder)