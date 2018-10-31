+++
title = "Introducción al GIS a través de QGIS"
date = 2015-02-04T23:47:34+01:00
draft = false

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["QGIS", "GIS", "Mapas"]
categories = ["Docencia", "Arquitectura"]

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
# Use `caption` to display an image caption.
#   Markdown linking is allowed, e.g. `caption = "[Image credit](http://example.org)"`.
# Set `preview` to `false` to disable the thumbnail in listings.
[header]
image = "post/intro_a_qgis.png"
caption = ""
preview = true

+++

A pesar de las numerosas bondades de los<a href="https://es.wikipedia.org/wiki/Sistema_de_Informaci%C3%B3n_Geogr%C3%A1fica" class="ext" target="_blank"><strong> Sistemas de Información Geográfica</strong></a> (SIG -o GIS en inglés) y de las aplicaciones directas que puede tener para el urbanismo, lo cierto es que no tengo constancia de que se enseñe en las facultades de arquitectura. Así pues, a día de hoy, los alumnos (y también muchos profesionales) siguen realizando los planos de análisis urbanísticos con programas de CAD para controlar la geometría y la representación y hojas de cálculo, ortofotomapas...&nbsp; Por no mencionar lo difícil (y costoso económicamente) que puede resultar conseguir una base topográfica de calidad para determinados emplazamientos o la gran cantidad de tiempo que requiere generar una buena representación final de estos datos, que de por sí no tienen ninguna relación.</p>
<p>Conscientes de esta problemática, <a href="http://etsa.usj.es/es/docentes/ana-ruiz-varona" class="ext" target="_blank">Ana Ruiz Varona</a>, profesora de Urbanismo y compañera del grupo de investigación Arquitecturas Opensource, y yo mismo, dedicimos programar una pequeña sesión práctica como parte de la formación extracurricular que venimos ofreciendo en la <a href="http://etsa.usj.es/es" class="ext" target="_blank">ETSA USJ</a> para introducir las bondades de los SIG a los alumnos de la escuela. Para ello preparamos un caso práctico que iríamos desarrollando a la vez que la sesión teórica mediante el programa <strong><a href="http://qgis.org" class="ext" target="_blank">gQIS</a></strong>, un excelente software de código abierto y multiplataforma de uso bastante extendido debido a su facilidad de uso y las funcionalidades que ofrece y apoyándonos en el movimiento opendata y los datos abiertos proporcionados por el Ayuntamiento de Zaragoza y el Gobierno de Aragón.</p>
<p>El objetivo del taller era confeccionar un mapa en el que se mostrase una ortofo de un Web Map Service (WMS) en la que se superpusieran las juntas municipales de Zaragoza, cada una de ellas representada con un color distinto en función de su densidad de población, además de mostrar el nombre de la junta y unos gráficos superpuestos con la evolución de población en los últimos años. Las <strong>diapositivas de la sesión y parte del resultado final pueden verse a continuación</strong>, si bien es posible visitar <a href="http://qgiscloud.com/ccamara/demo_curso_qgis_02" class="ext" target="_blank">este enlace a qgiscloud</a> con una versión más interactiva y funcional. También pueden descargarse los archivos de trabajo que acompañan a la presentación desde <a href="https://www.dropbox.com/sh/zfwnt0a9mulzixf/AACsI-jVrUSlZYs7CM2uN519a?dl=0" class="ext" target="_blank">este enlace</a>.</p>

<script async class="speakerdeck-embed" data-id="d9125475ecc94f8da93caea2aef9b5f7" data-ratio="1.33333333333333" src="//speakerdeck.com/assets/embed.js"></script>

<p>Así, durante casi tres horas de duración, vimos lo sencillo que puede llegar a ser realizar un ejercicio como el propuesto, apoyándonos en los datos abiertos proporcionados por el Ayuntamiento de Zaragoza y el Gobierno de Aragón, y relacionando toda esta información de orígenes, formatos y características distintas para lograr el resultado deseado.</p><p>La sesión tuvo muy buena acojida y los alumnos que asistieron a la sesión quedaron impresionados con las potencialidades del SIG en general y de qGIS en particular. Tanto es así que quedaron con tantas ganas de más que esperamos poder ofrecer una formación más completa sobre este software en el futuro, ya sea dentro del grado o como complemento formativo.</p>
<p><iframe src="https://m.qgiscloud.com/ccamara/demo_curso_qgis_02" width="100%" height="400px" frameborder="0">Ver versión completa</iframe>
