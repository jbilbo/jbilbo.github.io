---
title: Synaptics Touchpad y kernel 2.6
date: '2004-04-06T18:48:00.000-07:00'
tags:
- Software Libre
---

Parece que ser que el touchpad de mi portátil da problemas con el kernel 2.6. El caso es que no puedo hacer click ni scroll con el propio touchpad, tocando los botones de abajo sí funciona pero claro lo que más se utiliza es lo que no funciona (o al menos yo casi ni utilizo los botones de abajo).

Lo he solucionado instalando el driver synaptics (está masked en Gentoo pero funciona bien).

Se configura el /etc/X11/XF86Config añadiendo esto:

```
#sección para el touchpad
Section "InputDevice"
        Identifier "TouchPad"
        Driver "synaptics"
        Option "Device" "/dev/psaux"
        Option "SHMConfig" "on"
        Option "auto-dev"
        Option  "Emulate3Buttons" "yes"
EndSection
```

```
#sección para el ratón óptico normal
Section "InputDevice"
        Identifier  "Raton"
        Driver      "mouse"
        Option      "Protocol" "IMPS/2"
        Option      "ZAxisMapping" "4 5"
        Option      "Device" "/dev/mouse"
EndSection
```

Y luego en la última sección:

```
Section "ServerLayout"
        Identifier  "Server Layout"
        Screen "Screen0"
        InputDevice "Raton" "CorePointer"
        InputDevice "TouchPad" "SendCoreEvents"
        InputDevice "Keyboard0" "CoreKeyboard"
EndSection
```

Y listos... por ahora todo funcionando correctamente... (no testeado profundamente, esperaremos a que pasen los días... xD).
