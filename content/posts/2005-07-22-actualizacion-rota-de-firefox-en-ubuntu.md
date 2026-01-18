---
title: 'Actualización rota de Firefox en Ubuntu'
date: '2005-07-22'
tags:
- Software Libre
- Ubuntu
- Firefox
---

Hoy ha habido una actualización de seguridad de Firefox en Ubuntu por la mañana. El caso es según se comenta el paquete que corresponde a la versión 1.0.5 oficial de Firefox y parece que esa versión esta bastante 'cascá' (salió rápido la 1.0.6), almenos el paquete de Ubuntu correspondiente da una variedad de errores considerable (segmentations fault/violación de segmento, imposibilidad de instalar themes, extensiones rotas... yo he tenido que borrar mi profile (directorio $HOME/.mozilla) para poder arrancar el navegador... un desastre vamos).

Se ha abierto un thread con el fallo donde los usuarios comentan la jugada y una solución: Downgradear el paquete (volver a la versión de antes de actualizar) hasta que arreglen el nuevo o saquen la actualización correspondiente al 1.0.6 oficial:

```
$ sudo apt-get install mozilla-firefox=1.0.2-0ubuntu5 mozilla-firefox-gnome-support=1.0.2-0ubuntu5
```

PD: Escribid el comando en 1 línea. Cuando downgradeeis os servirá el profile antiguo así que no lo borreis y volverá todo a "como antes", con vuestras extensiones... etc.

**Actualización:** Ya han sacado un comunicado desde Ubuntu:

> yesterday a security update for Mozilla Firefox was relased (USN-149-1). Many users seem to have problems with the new version, it crashes very often.
>
> The problem is that one of the security patches changed the API (the interface that extensions use to integrate with the browser), which breaks many extensions. Similar problems happen with the upstream release 1.0.6, so using that does not help very much.
>
> To get an usable browser quickly, you have two options:
>
> 1) Uninstall extensions. Some extensions (like mozilla-tabextension, which is also packaged in Ubuntu universe) that rely on the old interface cause the browser to crash. Other extensions (like AdBlock) run fine.

La 2) es la que he comentado yo.

**Actualización 2**: Ya esta arreglado.
