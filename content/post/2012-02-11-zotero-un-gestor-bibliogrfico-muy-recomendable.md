+++
title = "Zotero: un gestor bibliográfico muy recomendable"
date = 2012-02-11T11:42:36+01:00
draft = false

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["zotero", "firefox", "libreoffice", "investigación"]
categories = ["Software"]
people = [""]

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
![Zotero](/img/post/zotero/zotero.png)

Aprovechando que el pasado 31 de enero salió la <a href="https://www.zotero.org/blog/zotero-3-0-is-here/">versión 3.0</a> del gestor bibliográfico <a href="https://www.zotero.org/">Zotero</a> me gustaría hablar de esta herramienta que se ha vuelto imprescindible para mi desde que la conocí de forma fortuita hace unos meses <a href="https://twitter.com/#%21/B_Espigares/status/104472980532379648">gracias a Twitter</a> (y de rebote conocí también Blanca Espigares, que fue quien me lo <a href="https://twitter.com/#%21/B_Espigares/status/104478437036666881">recomendó</a>).

{{< tweet 104478437036666881 >}}

### ¿Qué es Zotero?

Zotero es un servicio y un programa de código abierto desarrollado por la <a href="http://chnm.gmu.edu/">Roy Rosenzweig Center for History and New Media</a> para la <a href="http://en.wikipedia.org/wiki/Reference_management_software">gestión de fuentes bibliográficas</a> (libros, publicaciones, artículos de revistas, documentos, tesis, conferencias, webs, vídeos, capítulos de libros...), es decir te permite tener una biblioteca de recursos perfectamente organizada para poder encontrar la información que buscas de forma sencilla con tal de consultarla, citarla, anotarla o compartirla. Quien haya usado delicious, diigo, evernote o programas/servicios similares podría pensar que se trata de una alternativa más, sin embargo tiene una serie de particularidades que lo hacen mucho más recomendables para la gestión de recursos bibliográficos de lo que pueden llegar a ser estos (que están pensados para enlaces -diigo y delicious- o aspectos generales -evernote) y que trataré de explicar a continuación.<!--more-->
El funcionamiento de Zotero se basa en cinco conceptos que son a su vez sus mayores bazas:
1. Eecopilar
2. Organizar
3. Citar
4. Sincronizar
5. Compartir

### Recopilar

![](/img/post/zotero/store-anything.1252992817.png)

El primer paso para utilizar Zotero consiste en recopilar información y añadirla a la base de datos rellenando los múltiples campos necesarios para poder referenciar con garantías un recurso. El tipo de información que podemos archivar puede ser de cuatro tipos: Ficha bibliográfica; Notas; Archivos adjuntos o enlazados; Webs adjuntos o enlazados (ver imagen). El elemento más importante de todos es, sin duda, la ficha bibliográfica, que servirá, normalmente, como elemento "padre" del que colgarán el resto de elementos, y además tendrá los campos necesarios para identificar la referencia bibliográfica en cuestión. Estos campos varían en caso de tratarse de un libro, un capítulo de un libro, un artículo de una revista, una conferencia, una grabación... pero hay varios que son bastante fijos como son el título del recurso, el tipo, la fecha, la autoría (podemos añadir, además de autores, editores, colaboradores, traductores...), ISBN... Estos campos pueden rellenarse de forma manual (tarea que puede ser un tanto tediosa debido a que pueden añadirse muchos campos -si bien no todos son imprescindibles) o, ahora viene lo bueno, de forma automática a ya sea a partir de la introducción del identificador del recurso o a partir de metadatos de una página web.

Para añadir los datos a partir del identificador del recurso (es decir, a partir del <a href="http://es.wikipedia.org/wiki/ISBN">ISBN</a>, <a href="http://es.wikipedia.org/wiki/ISSN">ISSN</a>, <a href="http://www.doi.org/">Digital Object Identifier (DOI)</a>, o <a href="http://en.wikipedia.org/wiki/PubMed">PubMed ID</a>)&nbsp; basta con hacer click en el botón específico ![](/img/post/zotero/fetch.php_.png) e introducir el valor para que Zotero rellene automáticamente todos los campos. Tengo que decir que he podido comprobar que funciona bastante bien en general pero sin embargo en algunas revistas científicas españolas falla y en algunos casos en los que hay varios autores para un mismo recurso solo se añade el primero. Según puede leerse en la documentación esto es debido a que utiliza la base de datos de&nbsp; <a href="http://www.worldcat.org/">WorldCat</a> para ISBNs y <a href="http://www.crossref.org/">CrossRef</a> para DOIs, que si bien es bastante precisa, no está exenta de fallos.

![](/img/post/zotero/capture-research-data.1252992817.png) Cada vez que navegamos por una web que contiene metadatos, Zotero añade un icono al final de la barra de direcciones (ver imagen) que cambia en función de si se trata de un libro, un periódico, un sitio web, un blog... basta con hacer click en el icono para que Zotero rellene los campos de forma automática a partir de dichos metadatos. En caso de que la página contenga información sobre varios libros (como por ejemplo un artículo de la wikipedia en el que aparecen muchas referencias bibliográficas), aparecerá un cuadro de diálogo que nos muestra los títulos disponibles para que seleccionemos aquellos que queremos grabar . Si bien es cierto que la mayoría de webs no ofrecen este tipo de metadatos no es menos cierto que la mayoría de catálogos de bibliotecas, librerías online o algunos blogs (como este mismo) sí que los añaden. Además, cada vez que usamos este método se adjunta, automáticamente la página web que hemos consultado.

Por si no fuese poco, además, podemos importar elementos de otras bibliotecas en los siguientes formatos:
<ul><li class="level1"><div class="li">Zotero <acronym title="Resource Description Framework">RDF</acronym></div></li><li class="level1"><div class="li">MODS (Metadata Object Description Schema)</div></li><li class="level1"><div class="li">BibTeX</div></li><li class="level1"><div class="li">RIS</div></li><li class="level1"><div class="li">Refer/BibIX</div></li><li class="level1"><div class="li">Unqualified Dublin Core <acronym title="Resource Description Framework">RDF</acronym></div></li></ul>
o programas como <a href="https://www.zotero.org/support/kb/importing_records_from_endnote">importar items de Endnote</a>.

Una vez tenemos la ficha creada podemos añadirle elementos como notas, cuyo propósito es el mismo que los post-it o notas al margen que hacemos en los libros para apuntar ideas relacionadas, dudas, comentarios... que queremos recordar cuando revisemos el texto de nuevo. Resulta muy interesante también adjuntar o enlazar webs o archivos relacionados o incluso el archivo al que hace referencia la ficha (por ejemplo podemos adjuntar un libro electrónico o en PDF para poder consultarlo,&nbsp; o un documento de cualquier formato que hayamos creado). Esto tiene tres grandes ventajas: la primera es que podemos acceder fácilmente al contenido del recurso sin importar demasiado dónde lo habíamos almacenado, utilizando el buscador de zotero o navegando a través de la biblioteca, etiquetas o elementos relacionados. La segunda es que este archivo estará accesible remotamente (ver más adelante) y podremos acceder a él desde cualquier ordenador en el que tengamos instalado Zotero o tenga conexión a Internet. La tercera es que, en caso de adjuntar webs o documentos que puedan abrirse con el navegador web podremos subrayar o anotar comentarios al margen. Uno podría pensar que esta funcionalidad permite usar Zotero de forma muy parecida a <a href="http://db.tt/V1kXv09">dropbox</a> o <a href="http://sparkleshare.org/">sparkleshare</a> o <a href="http://owncloud.org/">owncloud</a>, y si bien es relativamente cierto, hay que decir que la cuenta gratuita solo cuenta con espacio para 100MB y, en caso de necesitar más espacio es necesario adquirir más megas.
Como dicen que una imagen vale más que mil palabras, el siguiente vídeo explica de forma mucho más visual y quizá más clara cómo funciona todo el proceso.

{{< youtube kqFiCj1XV-E >}}

### Organizar
![Biblioteca de Zotero](/img/post/zotero/zotero-library.png)
Una vez hemos añadido los recursos a la biblioteca es importante organizarlos para poder encontrarlos en el futuro y para ello ofrece cuatro funcionalidades muy interesantes: colecciones, etiquetas, elementos relacionados y búsquedas guardadas, además de tener, por supuesto, un buscador textual.</p><p>Las <strong>colecciones</strong> funcionan de forma similar a las colecciones de música de un reproductor multimedia: a diferencia de lo que ocurre cuando clasificamos elementos en carpetas, podemos añadir un mismo recurso a varias colecciones a la vez sin tener que duplicarlo. De esta forma, si tuviésemos las obras completas de Le Corbusier podríamos tenerlas archivadas en la colección "Arquitectos" y también en la de "Obras siglo XX" e incluso clasificar cada uno de los volúmenes en colecciones distintas. Además, podemos utilizar el buscador y <strong>guardar las búsquedas</strong> como si se tratasen de colecciones inteligentes o dinámicas (por ejemplo podemos grabar una búsqueda paar que muestre todos los elementos cuyo autor sea X persona o estén creados entre tal y cual año sin que tengamos que ir añadiendo manualmente cada elemento y así nos aseguramos de que esté siempre totalmente actualizado). Por si esto no fuese poco, las <strong>etiquetas</strong> ayudan&nbsp; a filtrar todavía más y de forma más concreta. Además, si añadimos un recurso a partir de metadatos, las etiquetas se añadirán automáticamente (luego podremos editarlas para añadir o quitar las que creamos convenientes).&nbsp; Finalmente podemos <strong>relacionar</strong> cada referencia con otras, y lo bueno que tiene Zotero es que si relacionas el elemento A con el B, automáticamente B se relaciona con A, lo cual ahorra trabajo y favorece notablemente la serendipia.

Además, recientemente en esta versión, Zotero incorpora una funcionalidad para encontrar duplicados, lo cual permite tener la biblioteca más ordenada si cabe.

### Citar

![](/img/post/zotero/word-and-openoffice-integration.1313408221.png) Sin duda este es uno de los puntos fuertes de los gestores bibliográficos en general y de Zotero en particular. Normalmente este tipo de programas se utiliza para poder recuperar la información almacenada y utilizarla para la redacción de artículos, investigaciones...&nbsp; Si bien la <a href="http://en.wikipedia.org/wiki/Comparison_of_reference_management_software">mayoría de gestores bibliográficos</a> permiten exportar uno o más items de la biblioteca para poder insertarlo en un procesador de textos, normalmente tienen dos limitaciones: la primera es que se trata de una exportación en lugar de una sincronización, con lo cual si añadimos nuevas referencias es necesario volver a exportar la bibliografía; la segunda es que si ofrecen algún tipo de integración (casi siempre unidireccional) con procesadores de textos siempre es con Microsoft Word. Zotero va mucho más allá y soluciona estos dos problemas de forma excelente: además de permitir exportar uno, varios o todos los elementos de la biblioteca en distintos formatos (rtf, html...) o al portapapeles, ofrece un plugin para <a href="https://www.zotero.org/support/word_processor_integration"><strong>integrarse con procesadores de texto</strong></a> como MS. Word y LibreOffice y OpenOffice. El plugin permite que, desde el propio procesador de textos, elijamos uno o más elementos bibliográficos de nuestra biblioteca (podemos utilizar un buscador como el de la imagen o bien navegar por ella) y los insertemos como cita y generemos automáticamente la bibliografía de todos los elementos citados en función de uno de los <a href="http://zotero.org/styles">más de 1600 estilos de citación</a> de los que dispone, entre los cuales se encuentran los habituales APA, ISO, Chicago Manual of Style... (y si no, siempre podemos crear nuestro propio estilo de citación). Lo maravilloso de este sistema es que de esta forma siempre tenemos la certeza de que bibliografía estará siempre actualizada, sincronizada con Zotero y será consistente en cuanto a su formato.
Como todo esto puede resultar un tanto complejo de entender, el siguiente vídeo presenta en acción la integración con procesadores de textos (el funcionamiento con Libreoffice o versiones más recientes de Word es totalmente análogo)

Además, por si no fuese poco, también permite la elaboración de fichas bibliográficas que son unos informes en los que muestra los datos de los elementos de forma ordenada y también contienen las anotaciones, resúmenes y etiquetas que hayamos podido hacer.

### Zotero como servicio

Para sacar el máximo partido a Zotero es necesario crearse una cuenta de usuario gratuita, de esta forma todo lo que almacenemos se guarda en nuestro ordenador y, también, en su servidor. Esto resulta muy interesante para aquellos quienes utilizan más de un ordenador de forma habitual, ya que de esta forma siempre tendrá la <strong>biblioteca sincronizada</strong> con independencia del ordenador que utilice y además también dispondrá de los PDFs o e-books que haya podido almacenar (por poner un ejemplo). En caso de utilizar un ordenador que no tenga instalado Zotero también podrá acceder, consultar y editar la biblioteca a través de la interfaz web, pudiendo añadir nuevos items (si bien es cierto que en este caso el proceso resulta un poco más tedioso).

Otra ventaja muy interesante de tener la biblioteca en un servidor remoto y tener una cuenta de usuario es que permite ofrecer ciertas funciones sociales tales como <strong>compartir colecciones</strong> (pueden ser públicas o restringidas a un grupo de usuarios). En las colecciones compartidas los colaboradores podrán consultar e incluso añadir elementos, comentarios... y también podrán participar en un foro, lo cual resulta muy interesante para investigaciones compartidas.</p><p>Para aclararlo un poco más podéis consultar <a href="https://www.zotero.org/c-c-m">mi perfil</a> y <a href="https://www.zotero.org/c-c-m/items">mi biblioteca pública</a> o los <a href="https://www.zotero.org/groups/">grupos</a> a los que pertenezco.

### Concluyendo

Si bien existen muchos gestores bibliográficos que son más conocidos (como por ejemplo <a href="http://www.refworks.com/">RefWorks</a> o Mendeley), las prestaciones y particularidades de Zotero lo convierten en una opción altamente recomendable. Además, las funciones sociales y el hecho de poder adjuntar archivos y subirlos a la nube permite utilizarlo de forma creativa para fines que no son los inicialmente previstos.

**Puntos fuertes**:

* Opensource (con todas las ventajas que eso supone a la larga y la posibilidad de participar traduciendo, documentando, añadiendo funcionalidades...)
* Multiplataforma (¡también disponible para GNU/Linux!)
* Integración con procesadores de textos, y muy en especial Libreoffice.
* Multiidioma (si bien todavía no he sabido encontrar la manera de traducir el estilo de citaciones al catalán)
* Mútliples estilos de citación: y si los más de 1600 no nos satisfacen, siempre podemos crearnos uno propio.
* Gratuito
* Se integra con el navegador (desde esta versión 3.0 permite integrarse con otros navegadores además de Firefox y también permite una versión independiente de navegador)
