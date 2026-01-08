---
title: 'Subtitulos en Mplayer'
date: '2005-10-10'
tags:
- Software Libre
---

Bajo Ubuntu Breezy no me salen los subtítulos en el mplayer, al parecer busca la fuente en ~/.mplayer/subfont.ttf.

Para resolverlo, le ponemos una fuente cualquiera como la Bitstream Vera:

```
ln -s /usr/share/fonts/truetype/ttf-bitstream-vera/Vera.ttf ~/.mplayer/subfont.ttf
```

![Mplayer subtítulos](/images/posts/mplayer-subtitles.png)

**Actualización**: Carlos Manso pone en los comentarios una forma más fácil:

```
aptitude install mplayer-fonts
```