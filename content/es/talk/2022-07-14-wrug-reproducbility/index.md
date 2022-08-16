+++
title = "Gestinando dependencias en R: automagic and renv"
publishDate = 2022-07-14T13:00:06+00:00  # Schedule page publish date.
draft = false
authors = ["admin"]

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date = 2022-07-14T18:00:00+00:00
#date_end = 2020-11-19T20:30:00+02:00

# Abstract and optional shortened version.
abstract = "En esta primera sesión del Grupo de usuarios de R de Warwick sobre reproducibilidad, presento dos métodos distintos para gestionar dependencias: {automagic} and {renv}"
summary = ""

# Name of event and optional event URL.
event = "Warwick R User Group"
event_url = "https://warwickrug.github.io/wrug_website/"

# Location of event.
location = "Coventry"

# Is this a selected talk? (true/false)
selected = false

# Projects (optional).
#   Associate this talk with one or more of your projects.
#   Simply enter the filename of your project file in `content/project/`.
#   E.g. `projects = ["deep-learning.md"]` references `content/project/deep-learning.md`.
#   Otherwise, set `projects = []`.
projects = ["wrug"]

# Tags (optional).
#   Set `tags = []` for no tags, or use the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["reproducibilidad", "R", "rstats", "Data Science"]

# Links (optional).
url_pdf = ""
url_slides = "https://ccamara.github.io/wrug-depedencies/slides.html#1"
url_video = ""
url_code = "https://github.com/ccamara/wrug-depedencies"

# Does the content use math formatting?
math = false

# Does the content use source code highlighting?
highlight = true

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
[image]
  placement = 2
  # Caption (optional)
  caption = ""

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Smart"

+++

Al final de la [sesión anterior del Grupo de Usuarios de Warwick R sobre revisión de código](https://warwickrug.github.io/wrug_website/posts/2022-05-25-2022-05-17-code-review/) tuvimos una interesante discusión sobre la necesidad de hacer código reproducible. Esta charla introduce el concepto de reproducibilidad y se centra en una de sus muchas facetas: la de la gestión de las dependencias de los scripts de 

Para ello, se presentarán, compararán y debatirán dos métodos diferentes: el sencillo pero funcional {automagic} y el más complejo, pero respaldado por RStudio, {renv}.

Al final de la sesión, se pondrán de manifiesto los puntos en común y las limitaciones, y se espera que se produzca un debate y se abra la puerta a la segunda charla de la serie sobre reproducibilidad.
