---
title: Añadir al path en MS-DOS y Linux
date: '2004-08-17T10:36:00.000-07:00'
tags:
- Tonteridas Mias
---

Siempre se me olvida cómo se hace en MS-DOS, los pongo como recordatorio que google ya me mira con mala cara :P<br/><br/>En MS-DOS, quiero añadir C:\TC\BIN al path:<br/><br/><pre>SET PATH=%PATH%;C:\TC\BIN</pre><br/><br/>En Linux, quiero añadir /home/bin al path:<br/><br/><pre>export PATH="$PATH:$HOME/bin"</pre>