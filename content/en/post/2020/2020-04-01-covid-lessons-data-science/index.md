---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Considerations on the importance of data and science in data science"
subtitle: "Learning data science with COVID-19"
summary: "When we are bombarded with figures and data on COVID-19, a reflection on how data is gathered, analised and visualized is a must if data is to be of any use at all."
authors: ["admin"]
tags: ["R", "dashboard", "COVID-19", "plotly", "flexdashboard"]
categories: ["Data Science"]
date: 2020-04-05T16:26:34Z
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Yet another COVID-19 dashboard. It may not be very insightful, but I love it because it's mine"
  focal_point: ""
  preview_only: false
  placement: 2

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []

gallery_item:
- album: img/showcase
  image: UKs COVID-19 Dashboard.png
  caption: "Total UK COVID-19 Cases Update Source: https://www.arcgis.com/apps/opsdashboard/index.html#/f94c3c90da5b4e9f9a0b19484dd4bb14"
- album: img/showcase
  image: NYT Coronavirus in the U S Latest Map and Case Count.png
  caption: "Map of OVID-19 Cases' growth in USA. Source: https://www.nytimes.com/interactive/2020/us/coronavirus-us-cases.html"
- album: img/showcase
  image: numeroteca_covid19_casos-registrados-por-comunidad-autonoma-superpuesto-log.png
  caption: "Numeroteca\'s Evolution of cases in Spain's regions, as part of an exhaustive analysis on Spain, France and Italy. Source: https://lab.montera34.com/covid19/"
- album: img/showcase
  image: numeroteca-small-multiples.png
  caption: "Numeroteca\'s Evolution of cases in Spain's regions, as part of an exhaustive analysis on Spain, France and Italy. Source: https://lab.montera34.com/covid19/"
- album: img/showcase
  image: WHO Health Emergency Dashboard.png
  caption: "WHO map. Source: https://extranet.who.int/publicemergency"
- album: img/showcase
  image: Table-decoration.png
  caption: "A table combining data with (rough) visualization. Source: [Carlos Cámara](https://ccamara.github.io/covid_spain/)"


---

I must confess: during these days of lockdown, I have been toying with dashboards and infographics about COVID-19 outbreak, just like everyone else.  [I have made an interactive dashboard](https://ccamara.github.io/covid_spain/) with nice plots, some formatted tables and even some (basic) maps. It's shiny and nice, you can spend some time playing with it turning layers on and off, hovering, zooming... And, honestly, I have to admit that I am proud of some of the results I have achieved. **And yet, it is flawed. Just like everyone else's** (or almost). And yet, I will keep improving it, even though I'm afraid it will always be flawed and even though I acknowledge that it will never be a contribution to improve knowledge on the topic.

Why, then, am I persisting on keeping working on it if I know I cannot change its fate? Admittedly, at some point, I asked myself that very question and I even considered quitting. Not only I didn't want to lose my time (even in these days when we are locked down at home there are plenty of things we can do), but I didn't want to contribute to generating noise, misinformation and even more dramatism about an already important drama. Because that's what flawed graphics do. But in the end, I realised that **working on a dashboard like that could be a great opportunity for learning by doing.**

Many types of lessons can be learnt from it, like those related to technical skills, or those related to how data is gathered, visualized and analyzed. **Today, when data and figures on COVID-19 are everywhere, I want to share some reflections on the science (or lack of it) in data science.**

## 1. Get the (right) data.

As obvious as it sounds, there is no data visualization nor data science without data to visualize or analyze. Therefore, the first thing that anyone who wants to make any type of data visualization or data analysis is to get the data. Second: we cannot use any type of data. We need to use _good data_, and **by _good_ I mean _reliable_, _usable_ (in terms of licences, formats and structure), up-to-date and frequently _updated_, and, hopefully, _official_ data that is _representative_ enough to explain the phenomenon we are studying.**  While this is usually non-trivial, it is even more crucial if we are to explain a completely new phenomenon that it is happening as we speak and it does at a global scale like COVID-19.

Usually, there are only two possible options[^infer]: either gather data by ourselves or rely on others' data. Whereas gathering our own data might be the best choice for some scenarios, in the case of COVID-19, it is unlikely that we are in a position to gather the kind of data that might be useful for us (in fact, even governments are struggling to do so, as we will see). Therefore, we are left to just one option. Of course, we cannot rely on some random person or institution, we need to rely on someone we can trust, like universities (because they tend to provide rigorous data), governments (because they provide official data) or organizations (like the [World Health Organization](https://www.who.int/emergencies/diseases/novel-coronavirus-2019)).  But where do we get the data from?

{{< figure src="img/WHO-dashboard.png" title="WHO's COVID-19 dashboard (Screenshot from 02-04-2020)" numbered="true" lightbox="true" >}}

While most governments provide data in open licences that allow its use and reuse for any purpose, they usually fail to address another important issue: the file format and data structure. As a result, in countries like the UK or Spain, data is not ready to consume as it is, without manual work[^data-formats]. Others, such as WHO, provide nice dashboards with data, but they do not provide the raw data to be consumed by 3rd parties. The good news is that there are people and institutions who are working in releasing clean data with open licences, such as [Datadista for data in Spain](https://github.com/datadista/datasets/tree/master/COVID%2019), [University John Hopkins](https://github.com/CSSEGISandData/COVID-19) that gathers data from different governments and WHO, and even [packages like this one for R](https://github.com/RamiKrispin/coronavirus) that fetches data from UJH and provides a nice data frame for developers and data scientists to use in their projects.

As a result, it is no wonder that most infographics and dashboards worldwide rely on the same data sources. It seems a sensible decision: not only we get data which is ready to use, but we do it from trustful sources. And yet, as I will argue, it is because of that reason that most of them are wrong. But what could possibly go wrong?


## 2. Don't take data too seriously

Now that we know where to get the data from, there is something we have to be aware of: by relying on data generated by others we have not solved the (main) problem of data gathering, we have simply transferred the responsibility to somebody else, but someone still has to deal with what we have been trying to avoid. And, surprise, not every country gathers the data in the same way.

Take the case of the most basic and crucial question: **how are the number of confirmed cases defined**. Since COVID-19's symptoms are very similar to those of influenza and the only way to know if someone is infected by it is by testing positive in the tests[^covid-tests]. This seems a great definition: we have an objective test which is same the for everyone and all countries seem to use the same criteria. Unfortunately, those tests require equipment which is scarce (compared to the current worldwide demand), can only be made in hospitals, and require up to two days to get the results. Therefore, there are many other scenarios that are not considered within this test, such as those shown in figure 2a. **So yes, every government provides that figure, yet all of them are much lower than the real figure. How much lower? There is no way to know.**

{{< figure src="img/iceberg.png" title="Confirmed figures ≠ actual figures. There are many more cases than the official ones. How many more? We can't possibly know" numbered="true" lightbox="true" >}}

Let's focus on another example: **the number of deaths by COVID 19**. Apparently, this should be easier. Every country keeps a record on the number of deaths per day and its cause of death, so it should be easy to filter those who died from COVID-19 amongst all the possible causes. Well, no. As we have seen, if we can't define with precision the number of people who are infected by COVID-19, we will not be able to know the number of people who have died as a result of it.

But it can be even trickier if we consider that every country has different criteria on how they count the number of deaths of people who were tested positive[^pais-muertos-covid]. Take the case of UK's definition:

>  The figures on deaths relate in almost all cases to patients who have died in hospital and who have tested positive for COVID-19.[...] These figures do not include deaths outside hospital, such as those in care homes, except as indicated above.[^uk-deaths]

So, again: real figures are much higher than those reported, no matter which country made the measurements. All of them are wrong. Some people argue that governments do not want to provide real figures not to create even more social alarm, lose popularity with their voters or even to look better than other countries. However, often the simpler answer is the most probable one[^occam]: it is not that governments want to hide information from us, it is just that no country has the means to face this outbreak, nor to mention to take accurate metrics. **And here lies another drama of COVID-19 that goes beyond the personal tragedy: no country in the world is prepared for the stress test that COVID-19 represents.**

![](img/conspiracy-mulder.gif)

{{< figure src="" title="It is not that Governments are conspiring hiding information, it is just that they do not have the means to get better figures. And here lies the drama!" numbered="true" lightbox="true" >}}

But let's go back to our path: that of data and figures. At this point, we have to acknowledge that all the data is flawed and we cannot get a perfect picture of the real situation out of them. If we wanted to do so, we would need to use other data sources, like comparing the record of total daily deaths[^momo] with the same period last year(s). Of course, this will need more time, and, in turn, this also has other implications and problems (for example, it will not give an accurate number of deaths by COVID-19, as there is no way to know their cause of death, but the significant difference between periods could be a good proxy).

So we have two options now, either losing faith completely in all COVID-19 infographics and metrics or to acknowledge their limitations and assume that they are just a rough approximation to reality.

{{< figure src="img/morpheus-red-pill.jpg" title="We have two options: either losing faith completely in all COVID-19 infographics or  assuming they are no more than a rough approximation to reality" numbered="true" lightbox="true" >}}

## 3. Choose the right figures and visuals

Great! If you are reading this it means that you are ok assuming that reality is (as always) far more complex than what nice dashboards can ever show, no matter how fancy they are. And speaking of that: **beware of fancy visuals!**

{{< gallery album="img/showcase" >}}

I'm sure that at this point you may have seen plenty of neat infographics of any type, like the ones above: some of them use boxplots, other lines, other scatterplots... some of them have smooth edges, others have axis with logarithmic scales. Even there are some that want to introduce geospatial analysis and present maps of different kinds (choropleths, bubbles, sizes)... and if you are like me, you can enjoy watching them and interacting with them during hours. But are they really effective to display useful data? Unfortunately, most of them are not (even some of my own).

One of the most basic yet frequent is to display a big figure of the total cases within a country. **Big figures are really catchy and easy to understand, but they usually lack some context to make them really meaningful**. Of course, anyone can understand that a 7-figure number is a big one, but it is really difficult to know how big it is. We need to compare it to something else to wholly grasp its real magnitude. Also, since we are dealing with a cumulative figure, knowing the analysed time span is a must, as it is not the same to reach a certain figure in one day, one week, one month or one year.

{{< figure src="img/big-figures.png" title="Big figures are really catchy and easy to understand but not really meaningful when used alone. This is something I tried to address by adding some context to them." numbered="true" lightbox="true" >}}

A common variation of that is to provide a line plot of cumulative cases, with the dates on the X-axis and total cases in Y-Axis. There are several variations of that: displaying relative data (eg: number of cases/population), with logarithmic scale (in order to make it easier to see the variations of the first days when compared to most recent ones), displaying several categories, either representing different regions or type of cases... Whereas they are really effective and most of them are right from a technical standpoint (especially considering that some of these variations make a great difference), it is the representation of figure itself that may be of little or no use. Is it really representative of something? What kind of questions can we answer by providing a number that, by definition, will always grow?

{{< figure src="img/WHO-cumulative.png" title="Line plot displaying cumulative cases. Is it really meaningful? Source: [WHO](https://experience.arcgis.com/experience/685d0ace521648f8a5beeeee1b9125cd)" numbered="true" lightbox="true" >}}

It is for that reason that some have decided to use other indicators in order to assess the evolution of the pandemic, such as the number of new cases per day, as they allow us to easily identify if figures are better or worse than the previous day.  Again, the same variations of the previous plots can be made in order to make this even more insightful, such as the following barplot, which displays the daily variation of cases, grouped by types. Not only we can see that they are starting to lower, but also, that the number of recovered cases is increasing over the deaths or active cases.

{{< figure src="img/cases_day_type.png" title="Daily cases, by type. Source: [Carlos Cámara](https://ccamara.github.io/covid_spain/)" numbered="true" lightbox="true" >}}

This is indeed more useful than cumulative cases, although it is somewhat volatile and can lead to confusion. Take the image below, as an example:

{{< figure src="img/weekend-effect2.png" title="Can you see that weird unexpected variation? It is the weekend effect! (That's why in the next dashboard version I will be highlighting the weekends). Source: [Carlos Cámara](https://ccamara.github.io/covid_spain/)" numbered="true" lightbox="true" >}}

Can you see how all figures suffer from a dramatic fall on 29th and 30th March just before peaking again the day after? This is indeed an unexpected behaviour and really difficult to explain. Unless we realise that those days were Saturday and Sunday, and due to the fact that there are fewer people working at hospitals, data is not taken as fast as usual and therefore, accumulates on Monday. This phenomenon has been called "the weekend effect" (Did I mention that you should not take data too seriously? :wink:)

It is because of that that some others, such as [John Burn-Murdoch](https://twitter.com/jburnmurdoch/status/1245822674418401282) from Financial Times, prefer to use a rolling average of a fixed period (such as 3 or 5 days), which is a more stable figure, such as that shown in the figure below.

{{< figure src="img/FT-rollingdata.png" title="Source: [Financial Times](https://www.ft.com/coronavirus-latest)" numbered="true" lightbox="true" >}}

Other techniques used to fix those outliers and display tendencies are to use smooth line plots based on the actual data, like the following plot made by [Pablo Rey](https://twitter.com/numeroteca).

{{< figure src="img/numeroteca-smooth.jpeg" title="Smoothed lines based on actual data. Source: [Montera34](https://lab.montera34.com/covid19/)" numbered="true" lightbox="true" >}}


## 4. Do not make hasty comparisons

Surely, the most frequent type of visual is that comparing how COVID-19 is affecting different regions, either within a country or comparing different countries (usually using China or Wuchan as a reference -after all, it is where it all started). While this kind of plots could provide answers to questions such as how a specific region is doing regarding another one (and therefore, replicating or avoiding their measures against COVID-19, for example), those comparisons are really problematic. For starters, the fact that population or size is largely different invalidates any comparison in absolute terms.

But even when using relative values (eg: number of cases per inhabitant), there are other key factors that have a direct impact on the evolution of the disease and its effects are assumed to be the same, while in reality can differ in several orders of magnitude, such as demography[^demography-covid], geography, urban settlements or health systems (in terms of human and financial resources), just to name a few.

{{< figure src="img/Diario_es_demografia_infectados2.png" title="Histogram of cases and mortality rates by age and country. Most cases in Italy were from 70-90, as opposed to 20-30 in South Korea, hence the enormous difference in the total of deaths. Source: [Diario.es](https://www.eldiario.es/sociedad/coronavirus-Italia-Espana-Corea-Sur_0_1007200429.html)" numbered="true" lightbox="true" >}}

**Amongst all those differences, though, the most relevant well may be the number of tests done to detect COVID-19, a figure that is not just different but also usually unknown**. This is by no means trivial, as we have seen that the number of cases is defined using this parameter. Therefore, if a country performed a really low number of tests, it will also have an extremely low number of cases. Out of sight, out of mind.

So, the biggest problem here is that without taking into consideration those factors, comparisons may render plenty of biased conclusions that have nothing to do with reality, such as come countries may be dodging COVID-19 or are kind of immune, or that COVID-19 only affects countries with a bad health system, unorganized governments, or undeveloped countries. As a result, **there is a risk of developing a narrative of moral superiority[^narratives] based on totally wrong foundations** like what some politicians have started to do in their own self-interest[^netherlands].

{{< figure src="img/repugnant-conclusions.jpg" title="Don't be like Wopke Hoekstra doing hasty comparison, or you risk reaching repugnant conclusions like him. Photo: [Teller Report](https://www.tellerreport.com/news/2020-03-31---hoekstra-guilty-after-criticism-italy---not-enough-empathetic--.ByGe3r0lP8.html)" numbered="true" lightbox="true" >}}


## 5. Take predictions even less seriously

The last group of plots, and the most complex ones, are those that make predictions. While they are really appealing and, apparently, provide answers to one of our main concerns (_"When is this going to end?" / Will this last any longer?_) in a very understandable way, they are really tricky. There are several ways to make predictions, such as using linear regression or models. While a model can be as easy[^predictions-r] or as complex as we want it to be (and as a result, their accuracy will differ dramatically), they mostly rely on having a good set of historic data or knowing the logics of the phenomenon they want to describe. Unfortunately, since COVID-19 is a new phenomenon, we are lacking of both, and therefore, predictions at this stage are prone to errors. Some predictions are based on what has happened in other places where the outbreak started before, but we have seen how problematic this can be.

{{< figure src="img/tarot.jpeg" title="If we can't see (nor understand) the model behind a prediction, it can be as useful and reliable as that of a fortune teller." numbered="true" lightbox="true" >}}

Last, but not least, we should not forget that they require a large amount of knowledge of a particular field something like most of the people who are doing those nice visualizations (including myself) lack of. Therefore, since I have openly admitted that this is something beyond my knowledge, at this point I can only but recommend to be sceptical about any prediction that is not made by an authority on the field. And even in that case (provided I could understand it), I would recommend caution. Or even better: just rely on predictions if they were made by an epidemiologist and you are one.

## Wrapping up

As argued, if data visualization is never easy, it is even less so in the case of a novel phenomenon such as COVID-19. Therefore, when facing any type of visuals, we should proceed with caution. If you are doing (or planning to do) any type of visualization, ask yousrself what question do you want to answer and which is the best way to do it, take into account the aforementioned considerations and make them evident to your readers[^considerations-medium]. Also, make your analysis reproducible, so anyone could tell you if you did something wrong or even fix it by themselves. If you are simply watching them, look for all those explanations, and if you can't find them, ask for them, help the author or simply ignore it and look for an alternative. But in any case, you should always remember not to take data too seriously or too blindly. Data by itself is not what really matters, is what we do with it and how we do it in order to achieve knowledge what really matters. And here's when science plays its role.

[^infer]: There is a third scenario: to infer or calculate the data from other datasets.
[^data-formats]: For example, [UK releases its data stored in a single XLS file](https://www.gov.uk/government/publications/covid-19-track-coronavirus-cases), without a clean structure. Not only they use a proprietary format, but they mix data with metadata on the same file, even in the same sheet, instead of using a wide format where every column is a field and every row is an observation or a long format where keys and values are stored as in a dictionary. On the other hand, Spain decided to release the data in PDF. PDFs are great for visualization because they are an ISO format and can be opened with plenty of different softwares. Unfortunately, it is not great for consuming data, as it is not structured in any way.
[^covid-tests]: At the time of writing this post, and according to [wikipedia](https://en.wikipedia.org/wiki/Coronavirus_disease_2019#Diagnosis)'s page, the [WHO has published several testing protocols for the disease](https://www.who.int/publications-detail/laboratory-testing-for-2019-novel-coronavirus-in-suspected-human-cases-20200117). The standard method of testing is real-time reverse transcription polymerase chain reaction (rRT-PCR), typically done on respiratory samples obtained by a nasopharyngeal swab and results are generally available within a few hours to two days.
[^pais-muertos-covid]: This article from El Pais (in Spanish) https://elpais.com/sociedad/2020-03-29/cada-pais-cuenta-los-muertos-a-su-manera-y-ninguno-lo-hace-bien.html
[^uk-deaths]: https://www.gov.uk/guidance/coronavirus-covid-19-information-for-the-public
[^occam]: This is the commonly phrased version of [Occam's razor](https://en.wikipedia.org/wiki/Occam%27s_razor) principle.
[^momo]: In Spain https://www.isciii.es/QueHacemos/Servicios/VigilanciaSaludPublicaRENAVE/EnfermedadesTransmisibles/MoMo/Paginas/Informes-MoMo-2020.aspx
[^demography-covid]: Refer to this ([excellent article in El Diario comparing Italy and China](https://www.eldiario.es/sociedad/coronavirus-Italia-Espana-Corea-Sur_0_1007200429.html) -in Spanish) which focuses on the fact that coronavirus mortality rate differs enormously according to the age.
[^narratives]: Refer to [The spread of the coronavirus across Europe against the right-wing Central European narrative](https://blogs.publico.es/otrasmiradas/30966/la-propagacion-del-coronavirus-por-europa-contra-la-narrativa-centroeuropea-derechista/) (Publico, in Spanish)
[^netherlands]: Take as an example the unfortunate words by Dutch finance minister Wopke Hoekstra, who suggested the EU "should investigate countries like Spain that say they have no budgetary margin to deal with the effects of the crisis provoked by the new coronavirus in spite of the fact that the eurozone has grown for seven consecutive years", a statement that was later qualified as "repugnant" by Portugal's Primer Minister, António Costa. (Source: [Politico](https://www.politico.eu/article/netherlands-try-to-calm-storm-over-repugnant-finance-ministers-comments/))
[^predictions-r]: Just to give you an example of how easy can be to implement a prediction in R, refer to this article: http://www.sthda.com/english/articles/40-regression-analysis/166-predict-in-r-model-predictions-and-confidence-intervals/
[^considerations-medium]: Also, reading this post may be useful: [Ten Considerations Before You Create Another Chart About COVID-1](https://medium.com/nightingale/ten-considerations-before-you-create-another-chart-about-covid-19-27d3bd691be8)
