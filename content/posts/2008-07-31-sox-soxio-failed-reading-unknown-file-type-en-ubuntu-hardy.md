---
title: "sox soxio: Failed reading unknown file type en Ubuntu Hardy"
date: 2008-07-31
tags: ["software-libre"]
draft: false
---

A partir de Ubuntu Hardy (que lleva Sox 14.0.0) se ha dividido el paquete de Sox, ahora sólo incorpora el núcleo mientras que los formatos de archivo soportados se han dividido en librerías. Mucho más limpio, pero si no lo sabes... te saldrá el error que he puesto en el título del post. Para solucionarlo hay que instalar los paquetes pertinentes, tenemos los siguientes disponibles:

```
libsox-fmt-all
libsox-fmt-alsa
libsox-fmt-ao
libsox-fmt-base
libsox-fmt-ffmpeg
libsox-fmt-flac
libsox-fmt-gsm
libsox-fmt-mp3
libsox-fmt-ogg
libsox-fmt-oss
libsox-fmt-sndfile
```

Si no sabes/dudas qué formatos vas a utilizar, puedes instalarlos todos instalando el metapaquete destinado a ello:

```
sudo apt-get install libsox-fmt-all
```

De esta manera es como estaba Sox antes, pero aprovechando que Sox se ha dividido podemos optimizarlo instalando tan solo las librerías que necesiteis según el formato. Por ejemplo si sólo vamos a trabajar con ogg, instalaremos:

```
sudo apt-get install libsox-fmt-ogg
```
