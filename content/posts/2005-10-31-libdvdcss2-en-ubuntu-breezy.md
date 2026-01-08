---
title: 'libdvdcss2 en Ubuntu Breezy'
date: '2005-10-31'
tags:
- Software Libre
---

Un
truco muy útil para los usuarios de Ubuntu Breezy, existe un script en
el sistema por defecto para facilitar la instalación del paquete
libdvdcss2 (que sirve para ver DVDs con algoritmo de encriptación, como
películas y demás). Para instalarlo:

```
sudo /usr/share/doc/libdvdread3/examples/install-css.sh
```

Este paquete no esta disponible en los repositorios por problemas
legales (no tengo claro si por patentes… el caso es que el que
descubrió cómo desencriptar el algoritmo de los DVDs lo hizo sin
permiso… y eso a los que controlaban quién podía reproducirlo y quien
no, no les hizo gracia). El otro dia lo hablaba con Sergio, si no fuera
por el que lo desencriptó… ahora mismo no se podrían ver pelis en DVD
en Linux… sería grave, ¿no?

Por cierto, la primera vez que utilizamos nuestro DVD se tiene que establecer la región. En linux lo podemos hacer así:

```
sudo aptitude install regionset
regionset
```

De todas formas, para los paquetes con problemas de licencias/patentes, os recomiendo [la página del wiki oficial de Ubuntu para los formatos restringidos](https://wiki.ubuntu.com/RestrictedFormats).