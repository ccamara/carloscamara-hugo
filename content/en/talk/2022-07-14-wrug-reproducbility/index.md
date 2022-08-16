+++
title = "Managing R script dependencies: automagic and renv"
publishDate = 2022-07-14T13:00:06+00:00  # Schedule page publish date.
draft = false
authors = ["admin"]

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date = 2022-07-14T18:00:00+00:00
#date_end = 2020-11-19T20:30:00+02:00

# Abstract and optional shortened version.
abstract = "In this first session of the WRUG reproducibility series, I introduce two methods to deal with library dependencies: {automagic} and {renv}"
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
tags = ["reproducibility", "R", "rstats", "Data Science"]

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

At the end of the [previous Warwick R User Group talk on code review](https://warwickrug.github.io/wrug_website/posts/2022-05-25-2022-05-17-code-review/) we had an interesting discussion on the need for reproducibility. This talk introduces the concept of reproducibility and focuses on one of it’s many facets: that of managing R script’s dependencies.

In order to do so, two different methods will be presented, compared and discussed: the simple yet works-out-of-the-box {automagic} and the more complex, yet backed up by RStudio, {renv}

At the end of the session, points in common as well as limitations will be highlighted, hopefully leading to a discussion and opening the door for the second talk of the reproducibility series.
