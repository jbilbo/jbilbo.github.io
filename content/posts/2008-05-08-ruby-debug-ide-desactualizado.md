---
title: 'ruby-debug-ide desactualizado'
date: '2008-05-08'
tags:
- Developer
---

ruby-debug-ide (o FastDebugger) es un paquete que utilizan algunos IDEs como [Netbeans](http://netbeans.org/) para depurar código ruby de manera eficiente a través de ruby-debug.

Ya hace unos días que ruby-debug-ide esta desactualizado en el
repositorio central de gems. Si actualizais ruby-debug y
ruby-debug-base os encontrareis con lo siguiente:

```
ERROR:  Error installing ruby-debug-ide:
        ruby-debug-ide requires ruby-debug-base (= 0.10.0)
```

Lo más lógico sería instalar la versión específica de ruby-debug que
te pide (0.10.0), pero no esta en el repositorio de gems (supongo que
el autor la debe de haber borrado y dejado sólo la última). Solución:
Bajárselo a mano de su [home](http://rubyforge.org/frs/?group_id=1900) y instalárselo :-) 

Bajamos los paquetes que nos pide ruby-debug-ide

```
$ wget http://rubyforge.org/frs/download.php/29708/ruby-debug-0.10.0.gem http://rubyforge.org/frs/download.php/29702/ruby-debug-base-0.10.0.gem
```

Esto desinstala cualquier versión que tuviéramos en el sistema

```
$ sudo gem uninstall ruby-debug ruby-debug-base ruby-debug-ide
```

Instala los paquetes

```
$ sudo gem install ruby-debug-base-0.10.0.gem ruby-debug-0.10.0.gem
```

Ahora sí, instalamos ruby-debug-ide

```
$ sudo gem install ruby-debug-ide
```