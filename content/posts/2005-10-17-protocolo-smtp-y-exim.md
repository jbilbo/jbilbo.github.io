---
title: 'Protocolo SMTP y Exim'
date: '2005-10-17'
tags:
- Software Libre
---

Nunca
me acuerdo del seguimiento que hay que hacer por telnet para enviar un
mail, es decir, del protocolo smtp… Los pasos son los siguientes:

```
helo localhost
MAIL FROM: yo@mail.org
RCPT TO: tu@mail.org
DATA
subject: esto es el asunto
Mira que esto es una prueba de mail y tal, para terminar
de escribir el texto lo debo acabar en punto, adios
.
quit
```

Y para continuar con el recordatorio… los comandos de consola de Exim4 más habituales:

*mailq* => Ver la cola de mensajes

*exim -qf* => Enviar mails de la cola

*exim -qff* => Enviar mail de la cola (incluído los “congelados”)

Logs de lo que pasa en: /var/log/exim4

Y por último:

```
exim -d mail@dealguien.org
esto es un cuerpo de mensaje
.
```

Para enviar mensaje desde exim activando el modo debug (mucha cantidad de información, útil para desarrolladores).