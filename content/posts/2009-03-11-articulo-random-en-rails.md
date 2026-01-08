---
title: Articulo random en Rails
date: '2009-03-11'
tags:
- Developer
---

Queremos obtener un registro aleatorio de la BD en Rails:

```ruby
def random
  @articulo = Articulo.find(:first, :order => 'RAND()')
end
```