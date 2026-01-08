---
title: Optimizando Ubuntu
date: '2004-11-12T05:52:00.000-08:00'
tags:
- Software Libre
---

Vereis que últimamente hago mucha referenia a Ubuntu, y es que el hecho de que la usemos en los cursos ha sido la excusa perfecta para migrar a esta distro. Ahora mismo estoy en fase de migración y todas las cosas que hacía con Gentoo todavía no puedo hacerlas con Ubuntu aún, pero eso es culpa mía, de que no tenía las cosas centralizadas como el correo. Ya que hago el paso... esta vez lo haré bien. De todas formas, aunque migre todavía no quiero perder el contacto con Gentoo, estaré testeando Ubuntu unos meses, y espero hacer el paso a Gnome 2.8 en Gentoo también... en fin, que por ahora estoy con las 2 pero trabajo en Ubuntu :)

Dicho esto... hoy me he encontrado con un [documento interesante](http://www.ubuntuforums.org/showthread.php?t=3713&highlight=MARK) (en inglés) para personalizar la distro después de la instalación (cómo instalar java prefiero la [manera del Sergio](http://www.ubuntu-es.org/book/view/55), que es más límpia), Yo me quedaré con las de optimización, que son 2:

**Desactivar IPv6 para que Firefox cargue las webs más rápido**

**Actualización**: En el link al documento original pone un método que no es el que funciona. Ver [este bug](https://bugzilla.ubuntu.com/show_bug.cgi?id=2443) y [este thread](http://www.ubuntuforums.org/showthread.php?t=171) en el foro.

Esta es la manera correcta (para kernels 2.6):

```
sudo sed -i -e 's/^alias *net-pf-10 *ipv6/alias net-pf-10 off/' /etc/modprobe.d/aliases
```

Este comando cambiará la línea de /etc/modprobe.d/aliases "alias net-pf-10 ipv6" y la pondrá como "alias net-pf-10 off". Así tendría que funcionar.

**Actualización2**: No funciona. Aún así, sigue cargando el módulo de ipv6. La manera más fácil y rápida (pero no más límpia) de que no lo cargue es cambiándole el nombre:

```
mv /lib/modules/2.6.8.1-3-686/kernel/net/ipv6.ko /lib/modules/2.6.8.1-3-686/kernel/net/ipv6.ko.bak
```

(Cambiad 2.6.8.1-3-686 por el nombre-version de vuestro kernel).

**Instalando un kernel específico para tu cpu**

Si tenemos la posibilidad de tener un kernel compilado para tu CPU, mejor. En mi caso (pentium4) es más optimo el linux-686 que el 386 que viene por defecto:

Para los nuevos Intel/AthlonXP:

```
sudo apt-get install linux-686
```

Para cualquier procesador AMD:

```
sudo apt-get install linux-k7
```

Para los procesadores Dual Intel:

```
sudo apt-get install linux-686-smp
```