---
title: 'Instal·lar suport d’Oracle oci8 i PHP a un servidor Linux'
date: '2006-02-07'
tags:
- Software Libre
---

**Amb PHP5**

Per conectar-nos a una Base de dades Oracle amb PHP desde Linux,
necesitem el mòdul oci8 pel php. La Base de dades Oracle pot estar a la
mateixa màquina o a qualsevol altre, això no importa.

Baixem els paquets “Basic” i “SDK” desde:

http://www.oracle.com/technology/tech/oci/instantclient/instantclient.html

Ara mateix, les versions són aquestes:

```
instantclient-basic-linux32-10.2.0.1-20050713.zip
instantclient-sdk-linux32-10.2.0.1-20050713.zip
```

Descomprimim els .zip i movem tot el que hi hagi dins la carpeta
creada “instantclient_10_2″ al directori /opt/oracle/instantclient

```
$ unzip instantclient-basic-linux32-10.2.0.1-20050713.zip
$ unzip instantclient-sdk-linux32-10.2.0.1-20050713.zip
# mkdir -p /opt/oracle/instantclient
# mv instantclient_10_2/*
# ln -s libclntsh.so.10.1 libclntsh.so
# ln -s libocci.so.10.1 libocci.so
```

Posem les llibreries al path:

```
# echo /opt/oracle/instantclient >> /etc/ld.so.conf
# ldconfig
```

Ara baixarem el mòdul de php amb PEAR i el compilarem i instal·larem:

```
# aptitude install build-essentials
# aptitude install php5-dev
# aptitude install php-pear

# mkdir -p /usr/local/src
# cd /usr/local/src
# pear download oci8
# tar xzf oci8-1.1.1.tgz
# cd oci8-1.1.1
# phpize
# ./configure --with-oci8=shared,instantclient,/opt/oracle/instantclient
# make
# make install
```

Ara el oci8 té la versió 1.1.1, però pot canviar més endavant.

Per habilitar el mòdul al php, introduïrem el següent:

```
extension=oci8.so
```

Als php.ini convenients (/etc/php5/apache2/php.ini i /etc/php5/cli/php.ini)

(p.e. es poden posar després dels exemples que comencen per ;extension).

Ara reiniciem l’Apache i ja es fan efectius els canvis.

```
# /etc/init.d/apache2 restart
```

Amb un phpinfo(); veurem que existeix el mòdul oci8.

Font: [http://ubuntuforums.org/showthread.php?t=92528](http://ubuntuforums.org/showthread.php?t=92528)

** Amb PHP4 **

Si volem també suport a php4, fem el següent:

```
# aptitude install php4-pear

# update-alternatives --config phpize

There are 2 alternatives which provide `phpize'.

  Selection    Alternative
-----------------------------------------------
*+    1        /usr/bin/phpize5
      2        /usr/bin/phpize4

Press enter to keep the default[*], or type selection number: 2
Using `/usr/bin/phpize4' to provide `phpize'.

# update-alternatives --config php-config

There are 2 alternatives which provide `php-config'.

  Selection    Alternative
-----------------------------------------------
*+    1        /usr/bin/php-config5
      2        /usr/bin/php-config4

Press enter to keep the default[*], or type selection number: 2
Using `/usr/bin/php-config4' to provide `php-config'.
```

Després procedim a compilar el mòdul igualment que amb php5, borrem
el oci-1.1.1 de abans i tornem a compilar desde un còpia neta.

```
# cd /usr/local/src
# pear download oci8
# tar xzf oci8-1.1.1.tgz
# cd oci8-1.1.1
# phpize
# ./configure --with-oci8=shared,instantclient,/opt/oracle/instantclient
# make
# make install
```

Per habilitar el mòdul al php, introduïrem el següent:

```
extension=oci8.so
```

Als php.ini convenients (/etc/php4/apache2/php.ini i /etc/php4/cli/php.ini)

(p.e. es poden posar després dels exemples que comencen per ;extension).

Ara reiniciem l’Apache i ja es fan efectius els canvis.

```
# /etc/init.d/apache2 restart
```