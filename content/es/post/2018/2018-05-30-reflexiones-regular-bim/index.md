+++
title = "Reflexiones sobre la necesidad de regular (o no) la obligatoriedad de usar BIM en obra pública."
date = 2018-05-30T21:21:22+02:00
draft = false

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Fundación Arquia", "BIM", "reflexiones"]
categories = ["Ciudad", "Tecnología", "Pensamiento y crítica"]
projects = ["blogarquia"]

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
# Use `caption` to display an image caption.
#   Markdown linking is allowed, e.g. `caption = "[Image credit](http://example.org)"`.
# Set `preview` to `false` to disable the thumbnail in listings.
[header]
[image]
placement = 2
caption = ""
preview = true



+++

Hace años, en 2009, [me preguntaba]({{< ref "/post/2009/2009-01-08-del-cad-al-bim.md" >}}) acerca de por qué el BIM, siendo que tenía una serie de ventajas innegables frente a trabajar con programas de CAD, apenas se utilizaba en España salvo en honrosas excepciones y contrariamente a lo que ocurría en otros países. Hoy, sin que tenga claro los motivos que han llevado a ello, la situación se ha invertido considerablemente y ya casi nadie se cuestiona su utilización, si bien no tengo claro que sea lo más utilizado, por lo menos aquí.

Seguramente tenga bastante que ver con este cambio de tendencia aspectos como el que leía recientemente (aunque probablemente no sea el único): la **[Ley 9/2017](https://www.boe.es/buscar/act.php?id=BOE-A-2017-12902&p=20171229&tn=1) determina la obligatoriedad de utilizar BIM en obra pública española a partir de 2018**. Dicha ley especifica que:

> “Para contratos públicos de obras, de concesión de obras, de servicios y concursos de proyectos, y en contratos mixtos que combinen elementos de los mismos, los órganos de contratación podrán exigir el uso de herramientas electrónicas específicas, tales como herramientas de modelado digital de la información de la construcción (BIM) o herramientas similares.[…]”.

A priori, a un defensor del BIM como yo[^1] debería parecerle una buena noticia, tal y como se ha difundido mayoritariamente, pero lo cierto es que me despierta muchas preguntas y no pocas reticencias.

La primera viene porque en ningún momento me queda claro a qué se refiere cuando habla de BIM o en qué debería traducirse finalmente: ¿se refiere a cualquiera de los softwares disponibles? ¿a uno en concreto? ¿o acaso se refiere a un formato de archivo? Me gustaría creer que, si efectivamente hablan de BIM como concepto, esto debería traducirse en aceptar cualquier tipo de archivo generado por alguno de los múltiples softwares de BIM existentes o, en su defecto, a uno de intercambio abierto, como IFC[^2].

Esto, que parece trivial, no lo es en absoluto, porque **si se obliga a utilizar una forma de trabajo que solo es posible desarrollar con un software concreto o bien se fuerza a un formato que no sea abierto y estandar, se está obligando, _de facto_, a utilizar un software específico, con las consecuencias tener que comprar (o incurrir en prácticas ilegales) y formarse para utilizarlo**. Condicionar la herramienta a utilizar no me parece una buena opción. Tampoco me lo parecía antes, cuando algunas administraciones solicitaban utilizar unas capas concretas, una forma de presentar específica… que delataban haber sido hechas con AutoCAD en mente, como si no hubiese otra solución posible y causando dificultades innecesarias a quienes usaban otros programas como Microstation, Archicad, Allplan… Entiendo que la administración debe asegurarse de poder abrir la documentación que recibe, pero de igual modo que no parece razonable esperar que tenga que pagar por todas las licencias de todos los programas posibles, tampoco lo es menos esperar a que una persona física tenga que hacer lo que la administración no ha querido. Es por ello que abogo porque las Administraciones deberían solicitar **formatos estándares abiertos**, como el **PDF** (ideal para estos casos, dado que no requiere de software específico, no admite modificaciones y permite visualizar con pequeñas interacciones) o, en el caso del BIM, el formato **IFC**.

Precisamente esto lleva al siguiente punto: No termino de entender por qué debe entregarse un proyecto arquitectónico en formato editable. **Los proyectos son documentos legales en los que la persona firmante adquiere unas responsabilidades por ello, y por tanto, facilitar un archivo editable firmado es lo mismo que firmar un contrato en blanco.** Pero aún hay otro motivo: entiendo que si se piden formatos editables es porque alguien, distinto al proyectista, quiere editarlo. Esto, que parece una perogrullada, tiene implicaciones profundas que tienen que ver con de quién es la **autoría de los proyectos** y quién tiene derecho a modificarlos, o con si los honorarios percibidos contemplan esas modificaciones o no y si estos son acordes con el trabajo realizado y las responsabilidades adquiridas, entre otros.

Pero ese debate lo dejaremos para otra ocasión o para los comentarios.

{{% alert note %}}
Este post fue escrito originalmente para el [Blog de la Fundación Caja de Arquitectos](http://blogfundacion.arquia.es/2018/04/reflexiones-sobre-la-necesidad-de-regular-o-no-la-obligatoriedad-de-usar-bim-en-obra-publica/)
{{% /alert %}}

[^1]: Ya en este artículo de 2009 abogaba por las ventajas de utilizar BIM frente a CAD (ahora matizo: por lo menos para proyectos de edificación, sobre todo si es obra nueva): http://www.carloscamara.es/blog/2009/01/08/del-cad-al-bim/
[^2]: A diferencia de los archivos rvt o pln, definidos y controlados en exclusiva por Autodesk y Graphisoft respectivamente, IFC organiza el modelo de datos (esto es, la manera en que se almacena la información) en un formato estándar y abierto desarrollado por el consorcio sin ánimo de lugro Building Smart orientado a favorecer el OpenBIM. Dadas esas características y al hecho de que no depende de ningún fabricante de software se garantiza, por tanto, que la información pueda intercambiarse entre distintos softwares de BIM sin que haya intereses ocultos para favorecer uno en detrimento de otro.
