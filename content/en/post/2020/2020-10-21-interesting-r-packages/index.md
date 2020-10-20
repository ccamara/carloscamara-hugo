---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Some R Packages I would love to explore (October 2020)"
subtitle: "A useful note for my future self (and probably to others)"
summary: ""
authors: []
tags: ["RStats"]
categories: ["Data Science"]
date: 2020-10-20T16:27:27+01:00
lastmod: 2020-10-20T16:27:27+01:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: true

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

These are some packages I have just discovered which I would like to try/use in the future. For future reference, I have added a brief description and links to source code:

## Data munging:

* [`janitor`](https://github.com/sfirke/janitor): has simple functions for examining and cleaning dirty data. It was built with beginning and intermediate R users in mind and is optimized for user-friendliness. Advanced R users can already do everything covered here, but with janitor they can do it faster and save their thinking for the fun stuff.
* [`rex`](https://github.com/kevinushey/rex) makes writing regular expressions easier by using a friendlier syntax. I always have some difficulties memorizing regex expressions and usually have to use the [Regex101](https://regex101.com/) (a great resource, by the way) as a reminder.
* the [`validate`](https://github.com/data-cleaning/validate) + [`errorlocate`](https://github.com/data-cleaning/errorlocate) + [`deductive`](https://github.com/data-cleaning/deductive) + [`dcmodify`](https://github.com/data-cleaning/dcmodify) team. These group of packages from the same author seem to work as a team. `validate` validates data's structure (It can even validate data [from rule files](https://cran.r-project.org/web/packages/validate/vignettes/rule_files.html) written in `yaml`), `errorlocate` finds the faulty observations, which can later be corrected by either `dcmodify` or `deductive` (from predefinded rules)

## Visualization:

* [hrbrthemes](https://github.com/hrbrmstr/hrbrthemes/blob/master/README.md) provides additional Themes and Theme Components for my beloved `ggplot2`.
* [`see`](https://github.com/easystats/see) provides additional color palettes and backgrounds for `ggplot`
* [`ggannotate`](https://github.com/MattCowgill/ggannotate): positioning annotations in `ggplot`.

## Geospatial:

* [`rmapzen`](https://github.com/tarakc02/rmapzen): a mapzen API client for R ([Documentation](https://tarakc02.github.io/rmapzen/)). I am always looking for good geocoding services (currently using [`photon`](https://github.com/rCarto/photon)), and this package uses Mapzen's Pelias geocoding (amongst other things).
* [`parzer`](https://github.com/ropensci/parzer) parses messy coordinates and converts from different formats to decimal. Also, provides helper functions such as getting hemisphere.