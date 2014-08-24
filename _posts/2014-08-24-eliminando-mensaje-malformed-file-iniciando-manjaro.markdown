---
layout: post
title:  'Eliminando mensaje "malformed" file al iniciar Manjaro'
date:   2014-08-24 09:31:04
categories: linux manjaro
---

Bueno ya les comente anteriormente que estoy muy contento con [Manjaro][manjaro] ya que me ahorro un buen tiempo de instalacion y puesta a punto de mi laptop, y es que en verdad me gusta mucho [Arch][arch] y sus derivados, en este caso instale la version que trae como interfaz a Cinnamon, la cual es mantenida por la comunidad.

Despues del proceso de instalacion encontre unos pequenos, pero molestos mensajes. Investigue un poco y no eran nada de que preocuparse pero no dejaban de ser molestos, asi que investigue un poco y logre corregirlos.

## Error de Grub "malformed" file

Bueno la verdad es que al arrancar Manjaro, despues de la pantalla de Grub en la que seleccionamos que sistema operativo queremos arrancar se presentaba el siguiente mensaje

	Grub error "malformed" file

Despues de eso se nos pide que presionemos cualquier tecla y el sistema funciona con total normalidad, pero no deja de ser incomodo.

Investigando un poco encontre que era un problema de ciertas versiones de Grub, y que se presenta sobretodo cuando tenemos una particion separada para */boot* y para solucionarlo podemos editar el archivo */etc/default/grub* y comentar la linea:

	# If you want to enable the save default function, uncomment the following
	# line, and set GRUB_DEFAULT to saved.
	GRUB_SAVEDEFAULT=true

dejandola asi:

	# If you want to enable the save default function, uncomment the following
	# line, and set GRUB_DEFAULT to saved.
	# GRUB_SAVEDEFAULT=true

Despues de guardar los cambios ejecutamos:

	sudo update-grub

Y al actualizarse la configuracion de Grub habremos eliminado el molesto mensaje

[arch]: https://www.archlinux.org/
[manjaro]: http://manjaro.org/
