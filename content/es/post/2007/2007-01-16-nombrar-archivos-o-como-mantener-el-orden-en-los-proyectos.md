+++
title = "Nombrar archivos (o como mantener el orden en los proyectos)"
slug = "nombrar-archivos-o-como-mantener-el-orden-en-los-proyectos"
date = 2007-01-16T00:16:41+01:00
draft = false

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["BIM", "CAD", "Herramientas digitales", "gestión", "favoritos", "análisis"]
categories = ["Arquitectura", "Software"]

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
# Use `caption` to display an image caption.
#   Markdown linking is allowed, e.g. `caption = "[Image credit](http://example.org)"`.
# Set `preview` to `false` to disable the thumbnail in listings.
[header]
image = ""
caption = ""
preview = true
+++

Los proyectos de arquitectura suelen desarrollarse en periodos largos de tiempo y generan un gran número de archivos y directorios. Si no hemos sido rigurosos y ordenados, la tarea aparentemente trivial de recuperar un plano concreto desarrollado hace unos meses o unos años (una situación bastante cotidiana en la profesión) puede convertirse en una auténtica odisea que puede desembocar en graves errores.

Mantener un orden de archivos y seguir un patrón al darles nombre que nos permita saber en todo momento y de manera rápida qué es lo que contienen cobran una importancia vial.

Este artículo se centrará en dar unos criterios para crear un código propio para nombrar los archivos de manera eficiente que nos permita saber el tipo de información que contiene, su versión, el proyecto al que pertenecen...

<!--more-->

{{% toc %}}

## Versiones anteriores
Soy partidario de no eliminar archivos antiguos, ya que el proceso proyectual a veces nos obliga a volver a soluciones que anteriormente habíamos desechado pero que por algún motivo vuelven a tener validez, eso origina un gran número de archivos y ponerles un nombre adecuado para identificar cual es la versión válida con la que deberemos trabajar puede ser complicado. Un sistema sencillo para identificarlos es añadir un número al archivo que nos permita identificar su número de versión. Sin embargo antes de aplicar este método tan sencillo en apariencia cabría hacer algunas consideraciones: *¿lo añadimos como prefijo o como sufijo? ¿la última versión será siempre la de número más alto? ¿cuantas versiones podemos tener de un mismo archivo?*

Por defecto, los sistemas operativos suelen ordenar sus archivos alfabéticamente, lo que puede hacer desaconsejable añadir un prefijo que determine el número de versión al nombre de archivo: si tenemos tres archivos (A, B y C) y cada uno tiene un par de versiones (1-A, 2-A, 1-B, 2-B, 1-C, 2-C)  al ordenarse alfabéticamente el orden sería este: 1-A, 1-B, 1-C, 2-A, 2-B, 2-C... y así sucesivamente.  Los archivos se mezclarían y estarían ordenados por el número de versión.

La tendencia habitual es la de ir añadiendo números a la última versión y cuanto más elevados sean será sinónimo de tener una versión más actual. Esto conlleva un problema cuando se trabaja con archivos vinculados o referenciados: al añadir un sufijo, el nombre del archivo cambia, y por lo tanto el vínculo se pierde o no se actualiza. Cambiar el vínculo no suele suponer mucho engorro pero es algo que no se debería hacer más que una sola vez (esa es la filosofía de los archivos vinculados al fin y al cabo). Una buena opción para evitar ese problema es que la última versión sea siempre la única que no tiene sufijo, y las copias serán las que se numeren. Cuanto mayor sea el número, quiere decir que la copia es más actual.

Otro sistema podría ser añadir una fecha al archivo, si bien esta información es redundante por estar en las propiedades de cada archivo, es mucho más fácil y rápida de leer. Pueden aplicarse las mismas reflexiones hechas anteriormente.

## Nombre del proyecto
Una opción interesante que puede facilitarnos el nombre de archivo es la de informar acerca del proyecto al que pertenecen. Esta información puede parecer algo redundante, pues los archivos suelen estar emplazados en un directorio que contiene esa misma información, sin embargo la experiencia dice que a veces los archivos no están en el sitio donde deberían estar (máxime si intercambiamos varios emails con nuestros colaboradores). Si a los proyectos les añadimos un código y a cada archivo le dotamos de ese código, será evidente si un archivo está fuera de su localización y será muy fácil moverlo al lugar correcto.

## Información del contenido
Este es quizá el aspecto más evidente del nombre de un archivo, pero no por ello menos importante: el archivo debe informarnos de qué tipo de información contiene sin que sea necesario abrirlo para ver si se trata de una memoria, un presupuesto, un plano de instalaciones o un render. Una breve descripción bastará para satisfacer este propósito, sin embargo hay que tener en cuenta que aunque los sistemas operativos actuales permiten escribir nombres de muchos caracteres no hay que abusar de ello. No hay que olvidar que lo que estamos intentando es leer en el menor tiempo posible la mayor cantidad de información posible. Además, se da el caso de que algunos programas no admiten nombres más largos de 21 caracteres + la extensión: si usamos nombres cortos nos ahorraremos problemas de incompatibilidades.
Otro método puede ser establecer un código de letras; puede que al principio sea engorroso y su lectura no sea tan inmediata, pero con el tiempo este sistema puede ser tremendamente eficaz a la vez que rápido.

## Otros datos
Algunas personas opinarán que además de todo lo expuesto anteriormente, el nombre de un archivo también debería dar información sobre si se trata de un archivo de arquitectura, ingeniería, urbanización... o de la fase de proyecto en la que se encuentran (estudios previos, proyecto básico, proyecto ejecutivo...), por dar algunos ejemplos.

## Consideraciones generales
Llegados a este punto, un error habitual suele ser el de idear un código que trate de dar solución a todos los temas que aquí se han planteado e incluso otros nuevos, lo cual suele ser contraproducente pues resultan en nombres de archivo muy complicados, largos y difíciles de leer. El método utilizado lejos de ser un sistema rígido e inmutable debe de ser lo suficientemente flexible como para permitir mejoras en  el tiempo, y para ello será imprescindible hacer un análisis exhaustivo de la realidad de cada uno que permita diseñar un sistema que satisfaga nuestras necesidades tanto presentes como las que preveamos que pueden ocurrir en un futuro no lejano y deseado.

Nombrar los archivos es algo muy personal y no existen fórmulas magistrales: el sistema que nos funciona de maravilla  puede no servirle para nada a otro despacho de arquitectura. La experiencia, propia o ajena (este artículo es un ejemplo de ello), será de gran ayuda en estos casos.

<strong>Autor:</strong> <a title="Ver página personal" href="http://carloscamara.es/perfil.html" target="_blank">Carlos Cámara Menoyo</a><strong>
Fecha: </strong>14/01/2007
<strong>Permalink:</strong> <a title="permalink" href="http://carloscamara.es/blog/2007/01/16/nombrar-archivos-o-como-mantener-el-orden-en-los-proyectos/" target="_blank">ver enlace original</a>
<strong>Contexto:</strong> A raiz de una consulta en el foro de <a title="Plusarquitectura" href="http://www.plusarquitectura.info" target="_blank">+arquitectura</a> decidí poner por escrito las reflexiones a las que había llegado respecto este tema durante mi experiencia laboral.
