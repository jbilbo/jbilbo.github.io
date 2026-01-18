---
title: 'Comenzando con Ruby On Rails'
date: '2006-04-19T01:11:00+02:00'
tags:
- Software Libre
---

La semana pasada empecé a trabajar en [Simpple](http://www.simpple.com/), la empresa donde hice el proyecto final de carrera. Estoy en un proyecto con [Ruby On Rails](http://www.rubyonrails.org/) y hablándolo con unos amigos he comentado lo fácil (almenos en Linux) que es instalar todo lo necesario para empezar a programar con Ruby y el framework RoR.

![RoR](/images/posts/rails.png)

He aquí los pasos para una Ubuntu Dapper (aunque el resto de distribuciones debe de ser equivalente pero con su sistema de paquetes):

Paquetes que necesitamos: (para ello, tiramos de paquetes propios del repositorio de Ubuntu)

```
$ sudo aptitude install ruby rdoc irb ri
```

También esta el paquete rails en Ubuntu para instalar, pero recomiendo instalarlo a mano. De esta forma no me ha dado ningún problema y podemos ir actualizándolo, rubygem se encarga de bajarnos todo lo necesario y instalarlo en el sistema muy limpiamente:

```
$ wget http://rubyforge.org/frs/download.php/11289/rubygems-0.9.0.tgz
$ tar -zxvf rubygems-0.9.0.tgz
$ cd rubygems-0.9.0
$ sudo -s
# ruby setup.rb
# gem install  rails --include-dependencies
```

Listo. Ya tenemos todo lo necesario... Basta un

```
$ rails aplicacion-ejemplo
```

Para generar el esqueleto y empezar a [toquetear por ahí](http://www.sobrerailes.com/pages/en_marcha_con_rails).

Y el servidor web (WEBrick) lo lleva ya integrado. Para encenderlo:

```
$ cd aplicacion-ejemplo
$ ruby script/server
```

Lo suyo es instalarse una Base de Datos, como MySQL:

```
$ sudo aptitude install mysql-server mysql-admin mysql-query-browser
```

\*Cuidado con el bug de mysql-admin. Para editar tablas, usad mysql-admin porque con mysql-query-browser ahora es imposible por culpa de otro bug.

Y un entorno de desarrollo como RadRails, un plugin para Eclipse:

```
aptitude install eclipse
```

Instalarse el plugin de [Radrails](http://www.aptana.com/) y [Subversion](http://subclipse.tigris.org/) (como un TortoiseSVN integrado), por ejemplo.

**Actualizado el 14-08-2006**
