---
title: 'Error actualizando a Ubuntu Karmic 9.10 desde Jaunty'
date: '2009-10-31'
tags:
- Software Libre
---

Hoy actualizando a la nueva Ubuntu me ha salido un curioso error:

*[Captura del error - imagen perdida]*

*Después de actualizar la información sobre los paquetes, ya no aparece el paquete esencial «ubuntu-minimal».

Esto indica un error serio; por favor, informe del fallo sobre el
paquete «update-manager» e incluya en el informe los archivos situados
en /var/log/dist-upgrade/.*

El bug [lo podemos encontrar](https://bugs.launchpad.net/ubuntu/+source/update-manager/+bug/446956) en el launchpad de Ubuntu con un montón de duplicados.

El problema no tiene nada que ver con la información que te da el error
(por eso lo de curioso), sino que simplemente se trata de un problema
de “conexión rechazada” por la sobrecarga que algunos servidores que
estan sufriendo por la recién salida de la nueva versión.

Por lo tanto hay 2 soluciones:

1.- Probar hasta que no pete (cuando peta simplemente se cancela y
te deja el sistema como antes sin sufrir ninguna modificación/daño). A
la segunda o tercera vez que le das suele funcionar pero el servidor de
descarga sigue estando sobrecargado y la velocidad a la que te bajas
los archivos es irrisoria.

2.- Cambiar los “mirrors” por otros que no esten sobrecargados, por
ejemplo los alemanes. Vamos a /etc/apt/sources.list y los cambiamos:

```
sudo gedit /etc/apt/sources.list
```

Sustituimos los servidores españoles (subdominio **es**) por los alemanes (subdominio **de**). Por ejemplo:

```
deb http://security.ubuntu.com/ubuntu jaunty-security main restricted universe multiverse
deb http://**es**.archive.ubuntu.com/ubuntu/ jaunty-updates main restricted universe multiverse
deb http://**es**.archive.ubuntu.com/ubuntu/ jaunty-proposed main restricted universe multiverse
deb http://**es**.archive.ubuntu.com/ubuntu/ jaunty main restricted universe multiverse
```

```
deb http://security.ubuntu.com/ubuntu jaunty-security main restricted universe multiverse
deb http://**de**.archive.ubuntu.com/ubuntu/ jaunty-updates main restricted universe multiverse
deb http://**de**.archive.ubuntu.com/ubuntu/ jaunty-proposed main restricted universe multiverse
deb http://**de**.archive.ubuntu.com/ubuntu/ jaunty main restricted universe multiverse
```

A mi me esta bajando a máxima velocidad :D