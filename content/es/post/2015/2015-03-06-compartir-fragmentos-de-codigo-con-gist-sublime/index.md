+++
title = "Compartir fragmentos de código con Gist y Sublime"
date = 2015-03-06T23:41:30+01:00
draft = false

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Sublime", "Gist"]
categories = ["Tecnología"]

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
# Use `caption` to display an image caption.
#   Markdown linking is allowed, e.g. `caption = "[Image credit](http://example.org)"`.
# Set `preview` to `false` to disable the thumbnail in listings.
[header]
[image]
placement = 3
caption = "Captura de pantalla de Sublime."
+++

**Como desarrolladores, a menudo nos encontramos realizando tareas repetitivas bastante parecidas (incluso a veces idénticas) a otras que hemos realizado anteriormente. En este post explicaré cómo mantener una biblioteca con control de versiones para poder encontrar fácilmente, reutilizar y compartir fragmentos de código con todo el mundo (o con unas personas determinadas) sin alterar demasiado el flujo de trabajo habitual.**

<p>Dependiendo de su complejidad, las <a href="https://drupal.org/best-practices" class="ext" target="_blank">buenas prácticas de Drupal</a> aconsejan&nbsp;<a href="https://drupal.org/documentation/modules/features" class="ext" target="_blank">utilizar features</a>, módulos personalizados o incluso perfiles de instalación para no repetirnos innecesariamente y ahorrar mucho tiempo y minimizar errores. Pese a todo, hay veces en las que solo queremos reutilizar pequeñas partes de código que hacen una funcionalidad muy pequeña o un efecto muy concreto y no vale la pena (o incluso es imposible) crear un módulo para ello. Este es el escenario perfecto en el que administrar una biblioteca de fragmentos de código puede sernos útil. Aunque es probable que ya tengamos nuestra propia biblioteca de código, eso no es suficiente si queremos compartirla con otros miembros del equipo o con la comunidad. Una manera de solucionarlo es&nbsp; utilizar dos herramientas bien conocidas:&nbsp;<a href="https://www.sublimetext.com/" class="ext" target="_blank">Sublime text</a> y los <a href="https://gist.github.com/" class="ext" target="_blank">Gist de Github</a>.</p>
<h3>Instalar y configurar el paquete Gist en Sublime</h3>
<p>Estas instrucciones asumen que ya tenemos instalado Sublime Editor y que ya tenemos una cuenta de usuario en Github. Si todavía no has hecho alguna de estas cosas hay muchos motivos para utilizar estas herramientas (de verdad) y hay mucha documentación sobre cómo hacerlo (al final del documento encontrarás algunos enlaces interesantes al respecto).</p>
<ol><li><strong>Instalar Package Control para Sublime Editor,</strong> que es un gestor de paquetes que facilita mucho la tarea de encontrar, instalar y actualizar paquetes dentro de Sublime. Para instalarlo basta con abrir la consola de sublime (ctrl<em>+</em>`) y pegar el código proporcionado en la web oficial, que además también incluye instrucciones más detalladas:&nbsp;<a href="https://sublime.wbond.net/installation" class="ext" target="_blank">https://sublime.wbond.net/installation</a></li>
<li><strong>Instalar el paquete <a href="https://sublime.wbond.net/packages/Gist" class="ext" target="_blank">Gist package</a> utilizando Package Control.</strong> Deberemos ejecutar la Command Pallete mediante la combinación de teclas ctrl<em>+</em>shift<em>+</em>p (Win, Linux) o cmd<em>+</em>shift<em>+</em>p (OS X) y escribir el nombre del paquete.</li>
<li><strong>Configurar el plugin de Gist</strong> para enlazarlo a nuestro usuario de Github.
<ol><li>Acceder a nuestra cuenta de Github y generar el token que se usará para el paquete Gist.<br>Puedes hacerlo haciendo clic en el enlace <a href="https://github.com/settings/applications" class="ext" target="_blank">https://github.com/settings/applications</a> y además, Github tiene una documentación muy ampliada sobre este aspecto en <a href="https://help.github.com/articles/creating-an-access-token-for-command-line-use" class="ext" target="_blank">esta pàgina</a>.</li>
<li>Abrir el archivo de configuración del plugin GIST y pegar el token que hemos creado en el paso anterior. Este archivo se abre automáticamente la primera vez que queramos ejecutar un comando desde la Command Pallete o puede encontrarse en el siguiente menú: Preferences/Package Control/Gist.</li>
<li>(Opcional) Rellenar el resto de configuraciones opcionales que proporciona el plugin, todas ellas detalladas en <a href="https://github.com/condemil/Gist#options" class="ext" target="_blank">este documento</a>.</li>
</ol></li>
</ol><h3>Utilizar el paquete Gist</h3>
<p>El paquete Gist proporciona una serie de opciones a las que podemos acceder a través de la Command Pallete. El nombre de todas es auto-explicativo pero las siguientes son las más utilizadas:</p>
<ol><li><strong>Insert a gist:</strong> muestra una lista de todos los gists de tu cuenta e inserta el contenido del gist seleccionado allí donde tengas el cursor.</li>
<li><strong>Open a gist:</strong> muestra una lista de todos los gists de tu cuenta y abre el archivo o archivos que contiene el gist en una o más pestañas, lo cual permite editarlos y actualizarlos (ver a continuación).</li>
<li><strong>Update a gist:</strong> actualiza el gist actual y hace push con los cambios al repositorio de gist.</li>
<li><strong>Create a private gist:</strong> crea un gist que solo será accesible por su creador y cualquier persona que tenga su url.</li>
<li><strong>Create a public gist:</strong> crea un gist público que puede ser visto, copiado, modificado y comentado por todo el mundo.</li>
<li><strong>Add a file into gist:</strong> añade el archivo que tengamos abierto y seleccionado como activo a un gist existente (recordemos que un gist puede contener uno o varios archivos).</li>
</ol><p>Utilitar el paquete de Gist es sencillo: basta llamarlo desde la Command Pallete y después seleccionar la opción deseada (Consejo: la mayoría de opciones proporcionan su atajo de teclado).</p>
<h3>Editar, compartir y comentar fragmentos de código en Gist</h3>
<p>Puede que sea un poco tarde para explicar esto ahora, pero los Gist son básicamente pequeños repositorios con una breve descripción que idealmente debería contener un archivo con un fragmento de código, aunque hay escenarios que requieren de varios de ellos. Las descripciones son muy importantes ya que son la única manera que tenemos para buscar (y encontrar) un gist en nuestro perfil o de entre los contribuidos por la comunidad. Eso quiere decir que la descripción debe ser realmente explicativa del contenido o tendremos problemas de verdad para encontrar nuestros propios códigos en el futuro (Consejo: podemos usar la # para marcar gists). Cada usuario tiene su propia página que muestra sus gists públicos (esta, por ejemplo: <a href="https://gist.github.com/ccamara" class="ext" target="_blank">https://gist.github.com/ccamara</a>) y también existe una página que muestra todos los gists públicos <a href="https://gist.github.com/discover/" class="ext" target="_blank">https://gist.github.com/discover/</a> que podemos usar.</p>
<p>Dado que se trata de un servicio basado en git, también tiene otras características interesantes:</p>
<ol><li>Posibilidad de marcar, observar o hacer fork de cualquier gist.</li>
<li>Posibilidad de comentar cada gist.</li>
<li>Posibilidad de clonar tu propio repositorio y trabajar en local con tus herramientas habituales, sin alterar demasiado tu flujo de trabajo habitual.</li>
<li>Posibilidad de editar gists desde el sitio web.</li>
<li>Posibilidad de insertar un gist en otra página, de forma que si alguna vez hay un cambio en el gist, sus modificaciones se mostrarán automáticamente, teniendo el gist siempre actualizado.</li>
</ol><h3>Bonus: motivos para usar Sublime text:</h3>
<p><strong>Pros:</strong> Bien documentado, multiplataforma, ligero, arquitectura extensible, comunidad y gran cantidad de plugins contribuidos, rapidez (multitud de atajos de teclado y comandos utilizando la Command Pallete)...</p>
<p><strong>Contras:</strong> No es opensource, no proporciona herramientas para debugar, no está pensado para OOP.</p>
<p>Si no conocías Sublime text o no lo utilizas, quizá te interese leer los artículos siguientes:</p>
<ul><li><a href="http://jkudish.com/2012/02/11/sublime-text-2/" class="ext" target="_blank">Why and how I use Sublime Text 2</a></li>
<li><a href="http://lamosty.com/2012/07/02/what-sublime-text-2-use-it/" class="ext" target="_blank">What is Sublime Text 2 and why you should use it.</a></li>
<li><a href="http://filipminev.com/post/14262857223/9-reasons-you-must-install-sublime-text-2-code-like-a" class="ext" target="_blank">9 reasons you must install Sublime Text 2.
