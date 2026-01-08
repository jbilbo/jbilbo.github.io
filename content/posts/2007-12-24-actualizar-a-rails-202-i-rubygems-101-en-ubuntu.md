---
title: 'Actualizar a Rails 2.0.2 i RubyGems 1.0.1 en Ubuntu'
date: '2007-12-24'
tags:
- Developer
---

Yo
siempre recomiendo tirar de Apt para ruby y librerías externas
(libopenssl, rmagick…) y de RubyGems para cosas más dinámicas como
Rails, Mongrel, Ferret… etc.

Pero a veces pueden ocurrir problemas en sistemas híbridos de este
tipo, como parece ocurrir al actualizar las rubygems a la 1.0.1.

Para actualizar a las últimas rubygems:

```
gem update --system
```

A mi en algún ordenador me dio algún problema de este tipo:

```
# gem -v
/usr/bin/gem:23: uninitialized constant Gem::GemRunner (NameError)
```

RubyGems quedaba totalmente inutilizable. El problema se esta discutiendo [aquí](http://www.ruby-forum.com/topic/136010#607028) pero hay una solución fácil que no implica instalar ruby 1.8.6 desde código fuente :-D 

Básicamente se trata de asegurarse que los script de rubygem esten
sólo en un sitio, en mi caso /usr/bin/gem* y no en /usr/local/bin/gem*
(si tienes éstos últimos los renombras a nombre_original.bak por ej.)

Después hacer un enlace simbólico de /usr/bin/gem1.8 (que es el bueno) a /usr/bin/gem (que no se ha actualizado bien). Así:

```
mv /usr/bin/gem /usr/bin/gem.bak
ln -s /usr/bin/gem1.8 /usr/bin/gem
```

Después de esto gem funcionará bien. Ahora toca instalar rails 2:

```
gem install rails
gem uninstall actionwebservice
gem cleanup
```

Después recomiendo reiniciar, no sé si es necesario pero a mi me dio
algún problema con una fixture y después de reiniciar no lo tuve :P