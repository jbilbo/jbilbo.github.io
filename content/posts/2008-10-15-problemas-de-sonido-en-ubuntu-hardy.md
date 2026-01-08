---
title: 'Problemas de sonido en Ubuntu hardy'
date: '2008-10-15'
tags:
- Software Libre
---

**Actualización:
A partir de Ubuntu Interpid (8.10) esto no es válido. Por mi parte todo
los problemas de sonido desaparecieron con la configuración por defecto.**

Recién actualizado a hardy me he encontrado algún problema con el
audio. Se ha introducido PulseAudio por primera vez en la distribución
justamente para solucionar los problemas comunes de audio que los
usuarios de linux venimos arrastrando desde los inicios del tiempo
(Alsa vs OSS vs ESD vs Arts), pero a su vez ha introducido otro…
esperemos que éste sea el definitivo.

La manera rápida de arreglarlo es poniendo como salida para toda
aplicación Alsa, pero entonces no utilizamos PulseAudio… y la idea es
integrarlo en todas las distribuciones y que se haga estándar lo más
rápido posible. Con estos sencillos pasos sacados de un [post de Ubuntu forums](http://ubuntuforums.org/showthread.php?t=789578) podemos tener PulseAudio funcionando bien:

Copia de seguridad de los archivos más importantes (si no los tienes saldrá un aviso, no pasa nada):

```
mkdir ~/pulse-backup; sudo mv ~/.asoundrc* /etc/asound.conf ~/pulse-backup/
```

Copiar los archivos de configuración de PulseAudio en tu directorio personal:

```
cp /etc/pulse/daemon.conf /etc/pulse/default.pa -t ~/.pulse/
```

Instalar los siguientes paquetes para asegurar que no te falta nada de PulseAudio:

```
sudo apt-get install libasound2 libasound2-plugins libasound2-dev padevchooser swh-plugins libao-pulse libsdl1.2debian-pulseaudio ladspa-sdk
```

Poner PulseAudio como “por defecto” para aplicaciones libao

```
echo "default_driver=pulse" >~/.libao
```

Abrimos el archivo siguiente:

```
gedit ~/.asoundrc
```

Y pegamos dentro este tocho:

```
pcm.!default {
  type pulse
}

ctl.!default {
  type pulse
}

pcm.pulse {
  type pulse
}

ctl.pulse {
  type pulse
}

pcm.equalized {
  type plug
  slave.pcm "equalizer";
}

pcm.equalizer {
  type ladspa

  # The output from the EQ can either go direct to a hardware device
  # (if you have a hardware mixer, e.g. SBLive/Audigy) or it can go
  # to the software mixer shown here.
  slave.pcm "plughw"
  #slave.pcm "plug:dmix"

  # Sometimes you may need to specify the path to the plugins,
  # especially if you've just installed them.  Once you've logged
  # out/restarted this shouldn't be necessary, but if you get errors
  # about being unable to find plugins, try uncommenting this.
  path "/usr/lib/ladspa"

  plugins [
    {
      label mbeq
      id 1197
      input {
       #this setting is here by example, edit to your own taste
       #bands: 50hz, 100hz, 156hz, 220hz, 311hz, 440hz, 622hz, 880hz,
       #       1250hz, 1750hz, 25000hz, 50000hz, 10000hz, 20000hz
       #range: -70 to 30
        controls [ -1 -1 -1 -1 -5 -10 -20 -17 -12 -7 -6 -5 -5 0 0 ]
      }
    }
  ]
}
```

En Sistema -> Preferencias -> Sonido pondremos como
“Reproducción de sonido” => “Autodetectar” (las 3) y como “Captura
de sonido” => “ALSA”.

Listo, reiniciar para que se carguen los archivos de configurar de nuevo y tendreis PulseAudio funcionando. 

Si teneis problemas con Flash, podeis hacer lo siguiente (Sólo para i386!):

```
sudo apt-get remove --purge flashplugin-nonfree
wget -c http://launchpadlibrarian.net/16150887/nspluginwrapper_1.1.0-0conn2_i386.deb
sudo dpkg -i nspluginwrapper_1.1.0-0conn2_i386.deb
sudo apt-get install flashplugin-nonfree libflashsupport
```

Para soporte de ecualizador y demás, pasaos por el [post este](http://ubuntuforums.org/showthread.php?t=789578) que lo explica bien (en inglés).