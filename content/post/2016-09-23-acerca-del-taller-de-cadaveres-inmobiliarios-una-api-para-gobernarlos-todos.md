+++
title = "Acerca del taller de Cadaveres Inmobiliarios: Una API para gobernarlos todos"
date = 2016-09-23T11:22:22+01:00
draft = false

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Cadáveres inmobiliarios"]
categories = ["Arquitectura", "Tecnología"]

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
[header]
image = "post/presentacion_cadaveres.jpg"
caption = "Presentación de Cadáveres Inmobiliarios en Medialab Prado, junto a Pablo Rey"

+++

<p>Desde que asistí al [Hackatón de Cadáveres Inmobiliarios]({{< ref "post/2016-02-12-hackaton-cadaveres-inmobiliarios.md" >}})
 <a href="/blog/2016/02/12/hackaton-cadaveres-inmobiliarios">Hackatón de Cadáveres Inmobiliarios</a> el pasado 11 de noviembre de 2015, quedé enamorado del proyecto debido a la cantidad y calidad de la información en su base de datos, por las múltiples posibilidades que ofrecía así como su enfoque colaborativo. Como recordaréis, en ese taller desarrollamos varios proyectos que consistían en visualización de los datos, pero quedaron algunos de ellos por desarrollar debido especialmente a la falta de tiempo. Uno de ellos fue la propuesta de crear un nuevo flujo de trabajo que facilitase la actualización y exportación de datos y que no incluyese pasos intermedios, tal y como muestra el esquema que posteriormente desarrolló <strong>Pablo Rey</strong>:</p>
<p><img alt="Workflow Cadáveres Inmobiliarios. Fuente: Pablo Rey." src="/img/post/cadaveres_workflow.png" title="Workflow Cadáveres Inmobiliarios. Fuente: Pablo Rey."></p><p>Como puede verse en el esquema superior, el flujo de datos que se utiliza actualmente almacena los datos en distintos lugares y requiere de procesos manuales para convertirlos a formatos que puedan ser aprovechados, lo cual supone tiempo y que los datos no estén siempre sincronizados, algo que no ocurrirá con el nuevo flujo ya que únicamente existirá una sola base de datos (ahora sí que será una base de datos) de la que podrán realizarse consultas, descargar datos en otros formatos e incluso utilizar una API.</p>
<p><img alt="Nuevo Workflow Cadáveres Inmobiliarios. Fuente: Pablo Rey." src="/img/post/cadaveres_workflow_new.png" title="Nuevo Workflow Cadáveres Inmobiliarios. Fuente: Pablo Rey."></p><p>Así pues, con esta idea en mente inicié un <a href="http://github.com/cadaveresinmob/c_inmobiliarios">prototipo en github</a> que, gracias al trabajo de <a href="http://twitter.com/numeroteca"><strong>Pablo Rey</strong></a>, <a href="http://twitter.com/skotperez"><strong>Alfonso Uzábal</strong></a> y <strong><a href="https://github.com/Ale-">Ale</a></strong>, ha ido madurando hasta ser funcional (aunque todavía falta trabajo por hacer y detalles por pulir) respecto al modelo de datos, formularios de creación y edición de contenido, histórico de versiones y una sencilla API REST. Aprovechando la existencia de dicho prototipo y de la celebración del segundo aniversario del proyecto, Pablo, Alfonso y yo propusimos un taller dentro del marco del <a href="https://arquitecturascolectivas.net/noticias/programacion-aacc-mad-2016">IX encuentro anual de Arquitecturas Colectivas</a> al que llamamos "<a href="http://cadaveresinmobiliarios.org/2016/09/12/una-api-para-gobernarlos-a-todos-cadaveres-inmobiliarios-arquitecturas-colectivas/">Una Api para gobernarlos a todos</a>" con varios objetivos. Además de explicar el proyecto a quienes no lo conocían, el primero de ellos era el de presentar al público por primera vez la nueva web y ponerla a prueba, para lo cual realizamos un proceso de beta-testing con los asistentes que tuvo buena aceptación y se detectaron algunos errores que pudieron ser subsanados (como por ejemplo el idioma del <a href="https://github.com/cadaveresinmob/c_inmobiliarios/issues/60">email de registro</a>) y otros se nos están resistiendo más (como el <a href="https://github.com/cadaveresinmob/c_inmobiliarios/issues/28">formulario de contacto</a>).</p>


{{< tweet 776099956566417408 >}}

{{< tweet 776079936226492418 >}}

<p>El segundo de ellos era introducir a los asistentes en la colaboración de proyectos open source, para lo cual <strong>Pablo</strong> hizo una pequeña introducción a GIT, Github (en especial el sistema de <a href="http://github.com/cadaveresinmob/c_inmobiliarios/issues">issues</a>), y presentó las distintas posibilidades de participación que ofrece el proyecto (tienes más información al respecto en <a href="https://github.com/cadaveresinmob/c_inmobiliarios/blob/master/contributing.md">este documento</a>), que incluye opciones tan variadas y aptas para todos los públicos como son <a href="https://github.com/cadaveresinmob/c_inmobiliarios/wiki/Manuales:-C%C3%B3mo-traducir">traducir la interfaz</a> (la nueva web será multilingüe), <a href="https://github.com/cadaveresinmob/c_inmobiliarios/blob/master/contributing.md#documentar">documentar</a> el proceso de edición y creación de cadáveres Inmobiliarios, <a href="https://github.com/cadaveresinmob/c_inmobiliarios/blob/master/contributing.md#testear">testear</a> y por supuesto ayudar con el desarrollo de la nueva web.</p>

{{< tweet 776441122650480640 >}}

<p>El tercero -y seguramente más espectacular y revolucionario- era el de presentar la nueva API de cadáveres inmobiliarios. Para ello, <strong>Alfonso</strong> hizo una introducción a qué es una <a href="https://en.wikipedia.org/wiki/Application_programming_interface">API</a>, los tipos distintos que hay y las posibilidades que ofrecen. Posteriormente hicimos una pequeña demostración de cómo está hecha la API de Cadáveresinmobiliarios (que actualmente es solo de consulta -GET- aunque esperamos mejorarla en el futuro para que permita modificaciones a aplicaciones autorizadas -POST), y la usamos para crear un mapa en la plataforma <a href="http://carto.com">Carto</a> que lee automáticamente los datos de la base de datos de cadáveres inmobiliarios y se actualiza automáticamente cuando se actualiza algún dato de la web.</p><p>La verdad es que la experiencia fue muy positiva y fue muy gratificante ver la aceptación que tuvo el trabajo realizado estos meses y, muy especialmente, las posibilidades que ofrece.</p><p>&nbsp;</p>
