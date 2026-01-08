---
title: 'Ripear con Sound Juicer con soporte mp3'
date: '2006-12-16'
tags:
- Software Libre
---

He encontrado  un tutorial en el [foro de Ubuntu](http://www.ubuntuforums.org/showthread.php?t=295698)
para hacerlo, pero con errores, aún así en los comentarios estan todos
solucionados. Aquí esta la “conclusión” (yo estoy con Ubuntu Edgy, con
Dapper debe ser muy parecido):

```
sudo apt-get install gstreamer0.10-plugins-ugly gstreamer0.10-plugins-ugly-multiverse
```

Abrir Sound Juicer, ir a Editar -> Preferencias -> Editar perfiles -> Nuevo

Lo elegimos y le damos a Editar:

```
Nombre del perfil: mp3
Descripció del perfil: Encode en mp3
Tubería Gstreamer: audio/x-raw-int,rate=44100,channels=2 ! lame name=enc bitrate=192 mode=Stereo ! id3v2mux
Extensión del archivo: mp3
Marcar ¿Está activo?

```

Si preferís menos espacio para los mp3 a costa de un poco de calidad
(que ni se nota…) cambiad el valor 192 por 128. Ahora reiniciamos Sound
Juicer y ya esta lista la opción para hacer encode a mp3 y que
autorellene los tags ID3 por defecto!

**Actualización 17/12/2006 - 17:58**: Siempre me olvido de la genial [Guía de Ubuntu](http://www.guia-ubuntu.org/index.php/Sound_Juicer), donde lo explican muy bien.