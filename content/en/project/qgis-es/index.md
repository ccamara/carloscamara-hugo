+++
title = "QGIS.es Website"
date = 2020-07-01T19:27:52+01:00
draft = false

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["hugo", "web", "QGIS", "maps", "CI"]

# Project summary to display on homepage.
summary = "Website development and CI infrastructure for QGIS' Spanish Association"

# Optional external URL for project (replaces project detail page).
external_link = ""

# Does the project detail page use math formatting?
math = false

# Does the project detail page use source code highlighting?
highlight = true

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
[header]
[image]
  placement = 3
  # Caption (optional)
  caption = ""

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Top"

+++

The creation of the new website of the [Spanish QGIS Association](https://qgis.es) presented two very different challenges. The first had to do with the content, since it was necessary to explain, on the one hand, QGIS as a project and, on the other what the Spanish QGIS Association is. Regarding the first goal, it was important to explain that [QGIS](https://qgis.org) is an Open Source Geographic Information System (probably the most advanced and widely used worldwide), as well as the different ways of collaborating with the project, emphasizing the fact that the website aims to become a meeting place for the international Spanish-speaking community. Regarding the second goal, it was necessary to explain what the Spanish QGIS Association is, what it does and how to become part of it to collaborate in the project.

{{< gallery album="gallery" >}}

On a technical level, it was necessary to respond to the need to easily update the contents, with the particularity that a CMS or dynamic websites could not be used in order to minimise costs in servers and time dedicated to updates and maintenance of the infrastructure. They also wanted a solution without lock in in terms of infrastructure, suppliers or technology.

All this led us to create a website with a static Hugo site manager hosted in a github repository and rendered from a continuous integration system. For the publication of content we opted for a workflow based on pull-requests and with a graphic interface through Netlify CMS.


