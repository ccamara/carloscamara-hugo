+++
title = "A brief note on maps and feminism"
date = 2019-03-08T15:10:07+01:00
draft = false

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["maps", "feminism", "genre"]
categories = ["General", "Claims"]
people = ["geochicas"]
projects = [""]

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
# Use `caption` to display an image caption.
#   Markdown linking is allowed, e.g. `caption = "[Image credit](http://example.org)"`.
# Set `preview` to `false` to disable the thumbnail in listings.
[header]
[image]
# Caption (optional)
caption = "Streets devoted to men and women in Barcelona. Source: Las calles de las mujeres, a Geochicas' project."

# Focal point (optional)
# Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
focal_point = "Smart"


[[gallery_item]]
album = "gallery"
image = "stats-barcelona.png"
caption = "Barcelona: Only 16% of the streets in Barcelona are named after a woman, as opposed to 83% wich are named after a man."


[[gallery_item]]
album = "gallery"
image = "stats-bsaires.png"
caption = "Buenos Aires: Only 6% of the streets are devoted to a woman."


+++

As those who know me well know, [I love maps](/tags/maps/): I like to see them, I like to make them and I like to use them to give answers to complex questions. I like the fact that you can create maps about almost anything. But surely, what I like most about them is that **they are unique tools to show unnoticed realities that help to understand all types of phenomena**. Some common (and, to some extent, hackneyed) examples of such maps are those used to explain the spread of diseases[^snow-map], the [distribution of energy consumption](https://data.worldbank.org/indicator/EG.USE.ELEC.KH.PC?view=map), social inequality, or [gentrification](https://www.theguardian.com/cities/2016/sep/30/worlds-most-gentrified-cities-crime-stats-coffee-shops). However, we can map any topic we can think of, and there are examples no less well known but important (on the contrary!), **such as gender inequality**.

That is why today, [March 8th, International Women's Day](https://en.wikipedia.org/wiki/International_Women%27s_Day), I wanted to highlight the excellent work they have done at [Geochicas](http://geochicas.org)[^geochicas], with the project [Women's Streets](https://geochicasosm.github.io/lascallesdelasmujeres/).

![Streets devoted to men and women in Barcelona. Source: La Calle de las mujeres, a project by Geochicas](featured.png)

*Women's streets* is paradigmatic because it makes a novel and necessary reading of an everyday reality for most of us who live in urban environments: the street nomenclator. By identifying the streets of some cities in Spain and Latin America whose names refer to women, and comparing it with the streets whose name refers to a men, they show that there is a great biass in the representation of women in public space. This is by no means trivial: since street names are often a way of celebrating (and recounting) the culture of a place by assigning names to influential and notable people or landmarks that have marked history, **such unequal gender representation evidences that the importance of women is systematically silenced, which contributes to building a story in which women have barely had an important role (or worthy of public recognition) in the historical and cultural development of our society**, which is clearly incorrect.

{{< gallery album="gallery" >}}

Another aspect of the project is to show how many of the women after whom a street is named have an article in the wikipedia (without evaluating its content). This also evidences that there is yet another gender gap which is not just a local matter of a few cities.

On the other hand, I cannot help but pointing out another issue that I love about the project (and for which I congratulate [Jess](https://github.com/jessisena), who has led its development), and it is its open development: since [the repository is available at github](https://github.com/geochicasosm/lascallesdelasmujeres), it is relatively easy to expand the information to other cities in the world, making the project even more useful, if possible.

<iframe width="100%" height="300px" frameBorder="0" allowfullscreen src="https://umap.openstreetmap.fr/ca/map/mapa-global-internaciona-feminista-8m-2019_298894?scaleControl=false&miniMap=false&scrollWheelZoom=false&zoomControl=true&allowEdit=false&moreControl=true&searchControl=null&tilelayersControl=null&embedControl=null&datalayersControl=true&onLoadPanel=undefined&captionBar=false"></iframe>

Other examples of maps that have dealt (although from other approaches) with the gender perspective are the [global feminist map of 8M 2019](https://umap.openstreetmap.fr/ca/map/mapa-global-internacional-feminista-8m-2019_298894#6/40.372/-2.900) (also made by geochicas), or the maps of feminist entities that exist in some cities [such as the one made by Barcelona City Council](https://ajuntament.barcelona.cat/dones/es/recursos-y-actualidad/mapa-de-entidades-feministas) or those that are collected in books such as [The Penguin Atlas of Women in the World](https://www.penguinrandomhouse.com/books/303719/the-penguin-atlas-of-women-in-the-world-by-joni-seager/9780143114512) by Joni Seager.

{{< figure src="unequal-opportunities.png" title="Unequal opportunities. From Myriad Edificions and Seager, J (2003. The Penguin Atlas of Women in the World)" >}}

Another similar, yet different, project linked to maps and gender perspective is the initiative promoted by Esther Mingot (a well-known mapper within the community of OSM Spain under the pseudonym of [Lanxana] (https://www.openstreetmap.org/user/lanxana)) to [import into OpenStreetMap all the centers in Catalunya devoted to provide information and care to women and LGBTI+ colective](https://wiki.openstreetmap.org/wiki/Import_information_and_care_points_for_women_and_LGTBI_collectives_in_Catalunya), out of several open datasources from Barcelona City Council and Generalitat de Catalunya. As a result, OSM map will become more inclusive and useful for those collectives.

All those examples outline another important feature about maps: maps can also be social transformation tools! (and I love it!)

[^snow-map]: It is famous the example of the map that Dr. John Snow made in 1854 to understand the spread of cholera in London. That map allowed to deduce that cholera was infected by polluted water rather than by air, as was thought at that time (For more information on the map, please read [this text by John Mackenzie] (https://www1.udel.edu/johnmack/frec682/cholera/cholera2.html) in which he explains how the map works and how to reproduce it with current GIS tools).
[^geochicas]: Geochicas is a group of OpenStreetMap women mappers aimed at closing the gender gap in that community.
