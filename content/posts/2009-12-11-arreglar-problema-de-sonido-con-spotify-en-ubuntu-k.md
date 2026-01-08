---
title: 'Arreglar problema de sonido con Spotify en Ubuntu Karmic'
date: '2009-12-11'
tags:
- Tonteridas Mias
---

**Actualizado a 16 dic 09.**

Os cuento como he arreglado unos problemas de sonido al ejecutar Spotify con Ubuntu 9.10 Karmic:

Primero de todo, aseguraos que en Sistema -> Preferencias ->
Selector de sistemas multimedia tenemos seleccionado PulseAudio:

Nota: En caso de que no te salga en el menú de Preferencias la
opción “Selector de sistemas multimedia”, significa que la tienes
desactivada del menú. Para activarla, hacemos clic derecho encima del
menú (encima de la palabra Sistema por ejemplo) y seleccionamos “Editar
los menús”. Desde el editor, en la sección Preferencias marcamos la
casilla de “Selector de sistemas multimedia” y le damos a Cerrar.
*[Captura del selector de sistemas multimedia - imagen perdida]*

```
$ sudo gedit /etc/apt/sources.list
```

Añadimos al final, en una nueva linea:

```
deb http://ppa.launchpad.net/neil-aldur/ppa/ubuntu karmic main
```

```
$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys D3E49C82
$ sudo apt-get update
$ sudo apt-get install wine1.2
```

Ya lo tenemos instalado. Ahora lo configuramos para que utilize PulseAudio:

```
$ winecfg
```

*[Captura de configuración Wine con PulseAudio - imagen perdida]*

Karmic utiliza por defecto PulseAudio como servidor de sonido y las
versiones de wine que llevan los paquetes oficiales de Ubuntu no
soportan todavía esta librería por lo que utiliza Alsa a pelo y hay
problemas. Esta versión de la 1.2 esta compilada con el soporte
necesario.

Nota aparte, para los que no tengais funcionando Spotify en Linux,
simplemente os bajais la versión Windows y abrís el instalador con
Wine, bien haciendo doble clic, o desde la terminal con:

```
$ wine Spotify\ installer.exe
```

Fuente: [3spoken](http://www.3spoken.co.uk/2009/08/making-wine-sound-work-with-pulseaudio.html)