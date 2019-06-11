+++
title = "Del CAD al BIM"
slug = "del-cad-al-bim"
date = 2009-01-08T00:16:41+01:00
draft = false

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["BIM", "CAD", "Herramientas digitales", "Cultura Digital", "gestión", "favoritos"]
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
![](/img/post/bim_0.jpg)
<strong><em>...si los arquitectos nos dejan...</em></strong>

A veces tengo la sensación de que, a pesar de lo que podría esperarse de una profesión creativa, los arquitectos somos reacios al cambio. Hace 15-20 años el sector de la construcción (y con él el de la arquitectura) vivió  toda una transformación: el uso de programas de CAD como punta de lanza en la introducción de la informática como  herramienta de trabajo principal. <strong>Cualquier cambio genera una oposición que será tanto más grande cuanto más de revolucionario tenga éste</strong>, y el caso que nos ocupa es un claro ejemplo de ello. Yo no viví lo que supuso abandonar el lápiz  y papel en su primera fase, era todavía bastante joven, pero sí que he podido vivir, años más tarde, los resquicios de la oposición que suscitó <!--break-->

Cuando accedí a la universidad, en 1998, el uso del CAD ya era algo cotidiano pero algunos de mis profesores se oponían a su utilización, ya que, decían, <em>"coartan la capacidad creativa y proyectual"</em>, algo que no ocurría con el uso de Rotring o lápiz y papel. No quisiera parar esta vez en un tema que me apasiona: la relación entre herramientas de trabajo, procesos mentales y obra construida. En su lugar recalcar solamente una cosa: me consta que hoy, 10 años más tarde, todavía hay arquitectos que defienden esta tesis, a pesar de que ya nadie se plantea realmente un entorno productivo basado totalmente en lápiz y papel. Actualmente el arquitecto que tenemos en nuestro imaginario no es esa persona sentada delante de una mesa inclinada con papeles vegetales y escuadra y cartabón, ese lugar lo ocupa una persona que trabaja con ordenador y que hasta lo consulta a través de un dispositivo móvil en la obra. Síntoma de que hay un cambio de paradigma que se ha asumido como hecho.

Y es que, ya lo decía <strong>Heráclito</strong>, nada permanece, todo cambia, algo que es especialmente cierto en el mundo de la tecnología. Lo que antes decíamos que se asumía como símbolo de modernidad ha quedado obsoleto. El CAD tiene que dejar paso al BIM. Nadie discute las ventajas que introdujo el uso del CAD: mejoraba considerablemente la velocidad de trabajo frente al papel, añadía la posibilidad de guardar y recuperar en cualquier momento la información para consultarla o incluso ¡imprimirla!, se podían corregir errores, hacía fácil la representación de elementos complejos en 3D... Tampoco se niega la revolución que supuso, pero si lo miramos fríamente (algo que solo permite hacer la distancia temporal) nos daremos cuenta de que la revolución fue relativa, pues no era más que la evolución lógica del lápiz y el papel: el primero se convertía en un ratón para introducir series de puntos con coordenadas en el espacio y el segundo en una pantalla. <strong>En ningún momento se cambió realmente la manera de trabajar, pensar y entender la arquitectura. </strong>No ocurre lo mismo en el caso del BIM.
<h3>¿Pero qué es el BIM?</h3>
Las diferencias entre BIM y CAD son más que notables, aunque a priori no parezca que hay ninguna porque ambos usan la misma máquina y un software muy similar en apariencia. Sin embargo el BIM no es una herramienta de dibujo, aunque sirva (también) para dibujar. Su mayor baza no es que permita trabajar más rápido, sino el<strong> almacenamiento de información y la relación que existe entre ella</strong>, que al fin y al cabo es de lo que hablan sus siglas: <em>Building Information Modelling </em>(o Modelización de la información del edificio). Esto que parece baladí, no lo es en absoluto pues tiene grandes ventajas, a saber:
<ul>
	<li><strong>Consistencia de los proyectos:</strong> cuando se hace un cambio, éste aparece reflejado en planta, alzado, sección... por tanto siempre habrá una consistencia entre todos los documentos que forman el proyecto, algo difícil de conseguir en el CAD. A decir verdad esto ocurre porque solo existe un único objeto: el modelo virtual, y las plantas, secciones, detalles... son representaciones de éste, algo que no ocurría literalmente con el CAD, pues cada uno de ellos eran entidades independientes.</li>
	<li><strong>Elementos con propiedades físicas:</strong> dado que en lugar de usar líneas, círculos... se representan elementos físicos tales como muros, techos, puertas, ventanas... éstos tienen la particularidad de que pueden dotarse de propiedades físicas tales como materiales, acabados, precios... y luego establer operaciones e informes con ellos.</li>
	<li><strong>Bases de datos relacionadas:</strong> las propiedades de los objetos se almacenan en una base de dato relacional, de tal manera que conociendo esos datos y el número de elementos que existen con cada una de estas propiedades, se pueden generar informes automatizados de recuentos de elementos constructivos (por ejemplo carpinterías) que además de ser casi instantáneos no darán opción a error y pueden actualizarse dinámicamente (no solo podemos cambiar algo en el plano y se cambiará en el informe sino que si lo cambiamos en el informe también cambiará en el plano)</li>
	<li><strong>Gestión de la información:</strong> un problema clásico del trabajo en CAD es la enorme cantidad de archivos distintos que se generan, llegando a dificultar enormemente la tarea de encontrar el archivo y la versión que necesitamos (<a href="http://carloscamara.es/blog/2007/01/16/nombrar-archivos-o-como-mantener-el-orden-en-los-proyectos/">1</a>) para trabajar o imprimir. El problema crece exponencialmente cuanto más complejo es el proyecto o mayor es el número de personas que trabajan en él. Con los programas BIM esto se facilita sobremanera y se facilita también el trabajo en grupo, la localización de información, impresión por lotes...</li>
</ul>
<h3>Retos de futuro</h3>
De lo comentado anteriormente se desprende un corolario interesantísimo:  Una de las mayores ventajas que ofrece el BIM es que al ampliar el tipo de información que admite y relacionarla entre ella, abre un gran número de posibilidades de crecimiento que hoy por hoy no existen pero podrían ser una realidad en un futuro muy próximo.  tales como:
<ul>
	<li>Dotar a los elementos constructivos de propiedades físicas que permitan calcular el comportamiento térmico del edificio en lugar de tener que usar programas de terceros como LIDER o CALENER que te obligan, además, a redibujar el edificio.</li>
	<li>Llevando la idea anterior más allá también podría funcionar para calcular las transmisiones de carga y el comportamiento estructural. El concepto es el mismo.</li>
	<li>Integrar la documentación escrita del proyecto con los datos del mismo. Actualmente las memorias descriptivas y constructivas requieren de la introducción de muchos datos técnicos del proyecto (cuadros de superficies, datos de agentes, datos del proyecto, presupuesto...). Estos datos podrían ser parte de la base de datos del modelo virtual e integrarse con las memorias, ganando, una vez más, tiempo y consistencia entre toda la documentación presentada.</li>
	<li>...</li>
</ul>
En resumen: como comentaba al principio del escrito, el BIM introduce un nuevo modo de entender el trabajo  en el que planos, datos, detalles... están relacionados entre sí formando un conjunto sólido, un modelo virtual del edificio del que se pueden extraer todo tipo de datos y representaciones, con el objetivo de incrementar la productividad y mejorar la seguridad de que lo que se representa es coherente y correcto. Ese cambio de modelo conceptual es a su vez su mayor enemigo, pues  supone, en efecto, un cambio en la manera de trabajar, y eso es algo a lo que muchos no están dispuestos a renunciar o simplemente no pueden. Es evidente que el cambio está a la vuelta de la esquina y será para bien. ¿Le abriremos las puertas los arquitectos?
<h3>Enlaces de interés y referencias:</h3>
1:  <a href="http://carloscamara.es/blog/2007/01/16/nombrar-archivos-o-como-mantener-el-orden-en-los-proyectos/">Nombrar archivos (o como mantener el orden en los proyectos) </a>

2:  En <a href="http://www2.csostenible.net/es_es/tclave/temames/Pages/bim.aspx" target="_blank"> este artículo</a> de la Agenda de la Construcció Sostenible se desarrolla más extensamente la idea de relacionar programas de BIM con el cálculo energético de los edificios.

Programas BIM:
<ul>
	<li><a href="http://www.archicad.es/" target="_blank">Archicad (Graphisoft)</a> <a href="http://www.archicad.es/" target="_blank">
</a></li>
	<li><a href="http://www.nemetschek.es/" target="_blank">Allplan (Nemetscheck)</a></li>
	<li><a href="http://www.autodesk.es/revitarchitecture" target="_blank">Revit (Autodesk)</a></li>
</ul>
