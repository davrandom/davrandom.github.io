---
layout: post
title: Regulador de parabrisas Touratech, mi experiencia
category: moto

excerpt: something

---

En junio 2015 compré una Yamaha Super Ténéré XT1200Z de segunda mano (2011). Como soy bastante alto, la pantalla normal no me cubre en los trayectos en autopista, mientras que con la pantalla más alta me faltan los clásicos dos dedos para estar bien cubierto.
Entonces mirando los acesorios de Touratech encontré un [soporte para el parabrisas](http://shop.touratech-españa.com/en/carenado-y-parabrisas/2339-regulador-del-parabrisas-con-barra-de-montaje-para-gps-para-yamaha-xt1200z-super-tenere.html#/combinacion-basica) de la XT1200Z que se puede regular en altura e inclinación. Vale al rededor de los 110€ ... no sale barato.


## Descripción del producto

El regulador está hecho de dos piezas metalicas, una que se atornilla al cuadro donde se atornilla la pantalla normalmente, y una otra pieza a la que hay que atornillar la pantalla. Las dos piezas deslizan una sobre la otra permitiendo regular la altura y la inclinación de la pantalla. Las dos piezas se aseguran entre ellas a través de cuatro tornillos que llevan una tuerca cada uno que se puede abrir y cerrar con los dedos.

El producto parece bien pensado y hecho.


## Mi experiencia de uso

La instalación es extremadamente fácil: sacar la pantalla, montar el soporte Touratech, montar otra vez la pantalla sobre el nuevo soporte. Diez minutos como mucho.

Parece que el producto esté bien pensado pero nunca probado en carretera. Ahora me explico.
Este producto tiene esencialmente dos problemas, a mi manera de ver:

1. Las tuercas que aseguran las dos piezas se destornillan con las vibraciones de la moto

2. Las arandelas y las dos piezas deslizan entre ellas, así que la pantalla vuelve a su inclinación mínima después de pocos kilómetros de autopista

Bueno ... sí es que soy un tiquismiquis.
Sí y no: si se destornilla una tuerca y te parte un tornillo mientras que estás conduciendo, os aseguro que no es nada divertido. Y es exactamente lo que me pasó a mi. Después del susto, escribí al servicio de postventa de Touratech España para saber como/donde encontrar una tuerca, tornillo y arandelas adecuadas.


## Servicio postventa España

Este es el correo que les envié:


_Buenos días,_

_hace un par de meses compré un regulador del parabrisas con barra de montaje para GPS para Yamaha XT1200Z Super Tenere. Después de montarlo y utilizarlo de he dado cuenta que los 4 tornillos que permiten regular la altura e inclinación del parabrisas no agarran bien (la pantalla vuelve a la inclinación mínima) y a veces se destornillan. Yo veo dos problemas:_

1. _las arandelas son demasiado lisas y deslizan sobre el metal, así que la pantalla vuelve en posición de mínimo ángulo con el viento_
2. _los tornillos se destornillan solos! habría que poner un final de recorrido en la tuerca._

_Mientras que estaba viajando una tuerca y el tornillo se soltaron y se volaron golpeando el deposito y los perdí. Fue un buen susto porqué no entendí enseguida lo que había pasado, pensé de haber perdido una pieza más fundamental. Además había vehículos detrás de mi y por suerte nadie se hizo daño._

_Pregunta: ¿donde puedo encontrar un tornillo y tuerca adecuados? (ya que son bastante peculiares)_

_Muchas gracias y un saludo_


Me contestaron muy rapidamente diciendome que pedian la pieza a la fábrica de Alemania. Después de poco me llegan las piezas a casa, parece todo perfect. Intento atornillar la tuerca al tornillo pero no acaba de atornillarse... uhm... aquí pasa algo raro!
La tuerca es de 4mm y el tornillo de 6mm!
Escribo un correo al servicio postventa. No me contestan.
Vuelvo a escribir un correo al servicio postventa. No me contestan.
Escribo un percer correo al servicio postventa. No me contestan.

Ok.
Ahora estoy cabreado y no hay manera de encontrar una tuerca apta.

Para el cabreado escribiré este articulo en 4 idiomas (lo siento si hay errores el Castellano no es mi idioma materno).
Para la tuerca emprimiré una con una impresora 3D.


## Emprimir una tuerca en 3D

He hecho un dibujo con OpenScad de la tuerca:

<a data-flickr-embed="true"  href="https://www.flickr.com/photos/davrandom/24447444169/in/dateposted-public/" title="Tuerca in OpenScad"><img src="https://farm2.staticflickr.com/1537/24447444169_f364b3e96e.jpg" width="486" height="442" alt="Tuerca in OpenScad"></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

La idea es que el plastico sirva como agarre para una tuerca normal y corriente en inox que pondremos dentro de este esqueleto de plastico.

Después he ido a un bar de Barcelona donde se pueden emprimir objetos en 3D, y aquí está la pieza:

<a data-flickr-embed="true"  href="https://www.flickr.com/photos/davrandom/24186766294/in/dateposted-public/" title="Tuerca"><img src="https://farm2.staticflickr.com/1568/24186766294_7f3a08ef37_z.jpg" width="536" height="640" alt="Tuerca"></a><script async src="//embedr.flickr.com/assets/client-code.js" charset="utf-8"></script>

El código fuente para esta pieza está [aquí](https://bitbucket.org/davrandom/misc_projects/src/4e7c5a98694037af93aa3a701b41f9e9929f51b1/3D_scad/?at=master); la pieza se llama touratech_grip y tenéis tanto el scad como el stl.


No estoy al 100% satisfecho con este diseño y en los próximos meses lo cambiaré bastante...


## Solucionar el deslizamiento de la pantalla

Una solucíon que no prevee poner arandelas más agresivas es poner una arandela de goma entre la placa del soporte y la arandela metálica que va a contacto con la tuerca. La foto lo explica mejor:

