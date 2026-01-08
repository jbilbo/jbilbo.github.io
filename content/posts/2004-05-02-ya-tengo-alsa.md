---
title: Ya tengo Alsa!
date: '2004-05-02T04:51:00.000-07:00'
tags:
- Software Libre
---

Hace unas semanas comenté que me era imposible conseguir tener alsa funcionando bien, porque aunque cuando lo configuraba me funcionaba luego se me quedó "mudo" y ya no volvía en sí. Ya sé cual era el problema, este fichero:

```
/etc/asound.state
```

Que guarda el volumen de todos los canales de audio. Este fichero se graba/restaura en cada "/etc/init.d/alsasound stop/start" (se descargan, cargan los módulos de sonido).

En mi caso el fichero tenía guardados valores cero de sonido y por eso no se me oía nada de nada. Y aunque usara "amixer" o "alsamixer" para cambiarlos, no había manera. La única solución era borrarlo.

```
rm -f /etc/asound.state
```

luego cargar alsa:

```
/etc/init.d/alsasound start
```

Ajustar el volumen (ahora está a cero)

```
amixer set Master 100 unmute
amixer set PCM 100 unmute
```

guardarlo en ese fichero que hemos borrado antes:

```
/etc/init.d/alsasound restart
```

Y listos... :)
