---
title: Configurar Apache2 con SSL en Ubuntu
date: '2004-11-16T19:28:00.000-08:00'
tags:
- Software Libre
---

Aunque supongo que es igual que con Debian, como siempre.

Instalamos Apache2:

```
apt-get install apache2
```

Habilitamos el módulo ssl:

```
a2enmod ssl
```

Ejecutamos un script para crear nuestro certificado de seguridad para el servidor (estará autofirmado).

```
apache2-ssl-certificate
```

Nos hará una serie de preguntas...

```
 # apache2-ssl-certificate

creating selfsigned certificate
replace it with one signed by a certification authority (CA)

enter your ServerName at the Common Name prompt

If you want your certificate to expire after x days call this programm
with -days x
Generating a 1024 bit RSA private key
........++++++
....................++++++
writing new private key to '/etc/apache2/ssl/apache.pem'
-----
You are about to be asked to enter information that will be incorporated
into your certificate request.
What you are about to enter is what is called a Distinguished Name or a DN.
There are quite a few fields but you can leave some blank
For some fields there will be a default value,
If you enter '.', the field will be left blank.
-----
Country Name (2 letter code) [GB]:ES
State or Province Name (full name) [Some-State]:Catalunya
Locality Name (eg, city) []:Tarragona
Organization Name (eg, company; recommended) []:jhernandez
Organizational Unit Name (eg, section) []:home
server name (eg. ssl.domain.tld; required!!!) []:jhernandez.gpltarragona.org
Email Address []:admin@jhernandez.gpltarragona.org
```

Ahora crearemos la configuración de "el sitio" para el servidor seguro basándonos en la que lleva por defecto:

```
cp /etc/apache2/sites-available/default /etc/apache2/sites-available/ssl
ln -s /etc/apache2/sites-available/ssl /etc/apache2/sites-enabled/ssl
```

/etc/apache2/sites-enabled/ssl tiene que empezar de la siguiente manera:

```
NameVirtualHost *:443
<VirtualHost *:443>
NameVirtualHost *:443
<VirtualHost *:443>
    ServerAdmin webmaster@localhost

    DocumentRoot /var/www/ssl.jhernandez.gpltarragona.org/htdocs
    <Directory />
        Options FollowSymLinks
        AllowOverride None
    </Directory>
    <Directory /var/www/ssl.jhernandez.gpltarragona.org/htdocs>
#[...aquí sigue...]
```

Tendreis que cambiar lo de directory según el directorio que queráis...

Ahora, /etc/apache2/sites-enabled/default también hay que configurarlo de la misma forma:

```
NameVirtualHost *:80
<VirtualHost *:80>
    ServerAdmin webmaster@localhost

    DocumentRoot /var/www/jhernandez.gpltarragona.org/htdocs
    <Directory />
        Options FollowSymLinks
        AllowOverride None
    </Directory>
    <Directory /var/www/jhernandez.gpltarragona.org/htdocs>
#[...aquí sigue...]
```

Ahora añade en el fichero /etc/apache2/ports.conf:

```
Listen 443
```

Por último, sólo basta añadir dentro del fichero "/etc/apache2/sites-enabled/ssl" en cualquier lugar (por ejemplo justo debajo de "ServerSignature On"):

```
SSLEngine On
SSLCertificateFile /etc/apache2/ssl/apache.pem
```

Reiniciamos apache2:

```
/etc/init.d/apache2 restart
```

Editado: [Artículo](http://www.gpltarragona.org/node/view/318) en gpltarragona.