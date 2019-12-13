+++
title = "Editing revealjs from markdown"
date = 2019-03-08T15:10:07+01:00
draft = true

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["reveal.js", "reports", "markdown"]
categories = ["Data Science"]
people = [""]
projects = [""]

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
# Use `caption` to display an image caption.
#   Markdown linking is allowed, e.g. `caption = "[Image credit](http://example.org)"`.
# Set `preview` to `false` to disable the thumbnail in listings.
[header]
[image]
placement = 3
# Caption (optional)
caption = "Streets devoted to men and women in Barcelona. Source: Las calles de las mujeres, a Geochicas' project."

# Focal point (optional)
# Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
focal_point = "Smart"


+++

In my previous post I explained...

In this one I will focus only one of the options: reveal.js and I will compare several ways to end up creating a nice presentation using reveal.js from a markdown text.
So with those requirements I continued my research and I got to know Reveal.js, which quoting from their repo is a

>A framework for easily creating beautiful presentations using HTML. Check out the live demo.
>
>reveal.js comes with a broad range of features including nested slides, Markdown contents, PDF export, speaker notes and a JavaScript API. There's also a fully featured visual editor and platform for sharing reveal.js presentations at slides.com.


## Reveal.js built-in markdown

Even though strictly speaking reveal.js file format is an html, it is also possible to use markdown for authoring content by adding a `data-markdown` attribute to any section, like this:

```
<section data-markdown>
	<textarea data-template>
		## Page title

		A paragraph with some text and a [link](http://hakim.se).
	</textarea>
</section>
```
Source: https://github.com/hakimel/reveal.js#markdown

However,

## Reveal.js built-in markdown (2)

In order to prevent very long files where configuration and content is mixed up, it is also possible to embed

## Reveal-md


## Hugo + Academic theme


Pros:



Cons:

* Does not allow

## Hugo + Reveal-hugo theme


## Reveal + Knitr
