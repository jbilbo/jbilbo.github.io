---
title: 'Actualizar RubyGems'
date: '2009-03-07'
tags:
- Developer
---

Para actualizar Gems es muy fácil, no requiere reinstalar el paquete. Primero miramos nuestra versión de gems con:

```
gem -v
```

Si gem os da error, probar con “gem1.8 -v”. En caso de que sí
funcione, podeis borrar /usr/bin/gem y hacer un link simbólico hacia
gem1.8:

```
sudo ln -s /usr/bin/gem1.8 /usr/bin/gem
```

Si tenemos gems >= 0.8.5, incorpora una manera directa de hacerlo:

```
sudo gem update --system
```

NOTA: Rubygems 1.1 y 1.2 tiene un bug que impide actualizar (sale
siempre “Nothing to update”). En caso de tener ese problema, lo haremos
de la manera antigua, que se muestra a continuación:

Para versiones anteriores (gems < 0.8.5), hay una gema que se encarga de ello:

```
sudo gem install rubygems-update
sudo update_rubygems
```