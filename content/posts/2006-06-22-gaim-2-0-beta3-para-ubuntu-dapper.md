---
title: "Gaim 2.0 Beta3 para Ubuntu Dapper"
date: 2006-06-22T18:50:00+02:00
tags: ["Ubuntu", "Linux", "Software Libre", "GNOME"]
---

Gracias a [Debuntu](http://www.debuntu.org/), una blog dedicado a sólo a trucos i curiosidades para [Debian](http://www.debian.org/) y [Ubuntu](http://www.ubuntu.com/), podemos instalar de forma fácil la última versión del programa de mensajería instantánea por excelencia en [Gnome](http://www.gnome.org/): [Gaim](http://gaim.sf.net/). A continuación los pasos con algunas capturas de esta nueva versión.

{{< figure src="/images/posts/gaim2beta3-1.png" alt="Gaim2.0 Beta3" >}}

Primero, abrir el archivo el archivo /etc/apt/sources.list. Desde la terminal:

```
sudo gedit /etc/apt/sources.list
```

y añadir la siguiente línea al final, se trata del repositorio donde esta el nuevo gaim.

```
deb http://repository.debuntu.org/ dapper multiverse
```

Y ahora un:

```
sudo aptitude update
```

Para actualizar la lista de paquetes disponibles en los repositorios y así "ver" el nuevo gaim del repositorio recién añadido.

Segundo, instalarlo. Si ya tenemos el gaim instalado de antes, bastará un:

```
sudo aptitude dist-upgrade
```

Si no lo tenemos:

```
sudo aptitude install gaim
```

Vereis que se instalan más paquetes que dependen, pero estos paquetes no son del repositorio nuevo, sinó de la propia Ubuntu. Así que únicamente se instalaran los paquetes gaim y gaim-data del repositorio de Debuntu (soy un poco maniático de no instalar paquetes ajenos... de esta manera es bastante limpio, con un aptitude remove gaim estamos como antes).

{{< figure src="/images/posts/gaim2beta3-2.png" alt="Gaim2.0 Beta3" >}}

Además, y lo recomiendo, podeis instalaros el bonito plugin de notificación de mensajes (parecido al guifications pero más "Gnome like"), llamado gaim-libnotify:

```
sudo aptitude install gaim-libnotify
```

Para activar el plugin teneis que ir a Herramientas -> Complementos y activar el "Libnotify Popups". Podeis configurar cuando quereis que salgan las ventanitas (esta en inglés). Las opciones son:
- Nuevos mensajes
- Sólo nuevas conversaciones
- Ignorar eventos de usuarios bloqueados
- Cuando un amigo se conecta

{{< figure src="/images/posts/gaim2beta3-3.png" alt="Gaim2.0 Beta3" >}}

Si usas mensajería instantánea con gaim, agradeceréis esta actualización, es mucho más bonito que la rama 1.x (el desplazamiento suave que hace cuando pones una linea nueva mola).
