---
title: 'Actualizar a Macromedia Flash 9 Beta en Ubuntu'
date: '2006-11-03'
tags:
- Software Libre
---

Sirve para Ubuntu dapper (6.06) y Ubuntu Edgy (6.10).
	

Abrir el fichero de repositorios:
	
```
sudo gedit /etc/apt/sources.list
```

	

Añadir este repositorio no oficial al final del archivo:
	
```
deb http://3v1n0.tuxfamily.org dapper 3v1n0
```

	

Actualizar el índice de paquetes:
	
```
sudo aptitude update
```

	

Actualizar el flash:
	
```
sudo aptitude install flashplugin-nonfree
```

	

Ya
se puede quitar la línea añadida antes a /etc/apt/sources.list y volver
a hacer un sudo aptitude update. Cerrar los Firefox i al abrir ya
tenemos nuevo flash, que no se desincroniza el video con el audio.
	

Sacado del [foro de Ubuntu](http://www.ubuntuforums.org/showthread.php?t=280313).