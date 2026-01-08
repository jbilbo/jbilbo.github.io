---
title: Desligar un proceso de una terminal
date: '2004-11-02T11:07:00.000-08:00'
tags:
- Software Libre
---

Cuando creamos un proceso en una terminal, este queda ligado a la terminal como "hijo". Si la terminal muere, también lo hace el proceso. Para evitar esto, si estamos en una terminal de escritorio (que es donde más se utiliza) podemos cerrar la terminal con el comando:

```
exit
```

y no cerrando la ventana. Esta es una de las formas que conozco, no sé si pasa lo mismo en las otras terminales que no sean gnome-terminal.

La otra forma, que es la "forma Unix" es con el comando:

```
disown
```

Si no le pasamos parámetros, cogerá el último proceso creado. También podemos pasarle como parámetro el PID del proceso si tenemos muchos. O pasarle estas opciones:

Desliga a todos los procesos ejecutados desde la terminal

```
disown -a
```

Desliga a todos los procesos ejecutados desde la terminal que esten en marcha (Running).

```
disown -r
```

Si os fijais, ejecutando el comando "jobs" vereis en todo momento los procesos que han sido ejecutados en la terminal. Si desligais un proceso desaparece del listado de "jobs". Para que el proceso se desligue de la terminal pero no se elimine de la lista de jobs podemos pasarle el parámetro -h al disown:

```
disown -h
```

Editado: [Artículo](http://www.gpltarragona.org/node/view/315) en gpltarragona.