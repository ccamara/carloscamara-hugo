---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Some thoughts on the importance of data and science in data science"
subtitle: "Learning data science with COVID19 #1"
summary: ""
authors: ["admin"]
tags: ["R", "dashboard", "COVID19", "plotly", "flexdashboard"]
categories: ["Data Science"]
date: 2020-04-01T17:46:34Z
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Yet another COVID19 dashboard. But I love it because it's mine"
  focal_point: ""
  preview_only: false
  placement: 2

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

I must confess: during these days of lock down, I have toying with dashboards and infographics about COVID19 outbreak, just like everyone else. And I am not ashamed to admit that I am proud of the results I have achieved: [I have made an interactive dashboard](https://github.com/ccamara/covid_spain) with nice plots, some formatted tables and even some (basic) maps. And yet, it is flawed. Just like everyone else's (or almost). And yet, I will keep improving it, even though I'm afraid it will always be flawed.  

Why, then, am I persisting on keeping working on it if I know I cannot change its fate? Admittedly, at some point I asked myself that very question and I even considered quiting. Not only I didn't want to lose my time (even in these days where we are locked down at home there are plenty of things we can do), but I didn't want to contribute to generate noise, missinformation and even more dramatism about an already important drama. Because that's what flawed graphics do. But in the end, I realised that working on a dashboard like that could be a great opportunity of learning by doing.

So far, I have learnt two types of lessons: those related to technical skills, and those related to data in all its lifetime: from data gathering to visualization and analysis. Today, I will write about the latter.

## Lesson 1: Get the (right) data.

As obvious as it sounds, there is no data visualization nor data science without data to visualize or analize. Therefore, the first thing that anyone who wants to make a data visualization or data analysis is to get the data. Second: we cannot use any type of data. We need to use _good data_, and **by _good_ I mean reliable, usable (in terms of licences, formats and structure), up-to-date and frequently updated, and, hopefully, official data** that is representative enough to explain the phenomenon we are studying. While this is usually non-trivial, it is even more crucial if we are to explain a completely new phenomenon that it is happening as we speak and it does at a global scale like COVID19.

Two options[^infer]: either gather data by ourselves or rely in others' data. Whereas gathering our own data might be the best choice for some scenarios, in the case of COVID19, it is unlinkely that we are in a position to gather the kind of data that might be useful for us (in fact, even governments are struggling to do so, as we will see). Therefore, we are left to just one option. Of course, we cannot rely in some random person or institution, we need to rely in someone we can trust, like universities (because they tend to provide rigorous data), governments (because they provide official data) or organizations (like the [World Health Organization](https://www.who.int/emergencies/diseases/novel-coronavirus-2019)).  but where do we get data about ? Furthermore, where do we get ?

While most governments provide this data in open licences that allow its use and reuse for any purpose, they usually fail to address another important issue: the file format and data structure.
* Format:
  - UK -> XLS without a clean structure (rows and columns), instead, they use a proprietary format, and they mix data with metadata on the same file, even in the same sheet, instead of using a wide format where every column is a field and every row is an observation or a long format where keys and values are stored as in a dictionary.
  - Spain: PDF. PDFs are great for visualization because they are an ISO format and can be opened with plenty of different softwares. Unfortunately, it is not great for consuming data, as it is not structured in any way.
  - Others, such as WHO provide nice dashboards with data, but they do not provide the raw data to be consumed by 3rd parties.
  - The good news is that there are people and institutions who are working in providing clean data with open licences, such as Datadista for data in Spain, University John Hopkins that gathers data from different governments and WHO, and even packages like this one for R that fetches data from UJH and provides a nice dataframe for developers and data scientists to use in their projects.

With this panorame, it is no wonder that most of infographics and dashboards worldwide rely on the same data sources. It seems a sensible decision: not only we get data which is ready to use, but we do it from trustful sources. What could possibly go wrong?

 And yet, as I will argue, it is because of that reason that most of them are wrong.

## Don't take data blindly/too seriously

Now that we know where to get the data from, there is something we have to be aware of: by relying on data generated by others we have not solved the (main) problem of data gathering, we have simply transfered the resposnsability to somebody else. Someone still has to deal with what we have been trying to avoid.

![](iceberg.svg)

Probably, the main problem underlying on every single plot, infographic  is that they use the same data sources and

Starting from the most obvious: at a personal level, I have learnt a big deal of new techinical skills that I didn't have just a week ago. To be more precise, I have learnt:

1. To create a nice dashboard with some interactions within a single `rmd` file using `R`'s [`flexdashboard`](https://rmarkdown.rstudio.com/flexdashboard/)
2. To host and deploy the dashboard using github pages, just by committing and pushing to [my github's repo](https://github.com/ccamara/covid_spain)
3. To use [`plot.ly`](https://plotly.com/) for interactive plots instead my good old `ggplot2`, which I have come to love. This is something I had wanting to do for quite a long time but I had never had the chance nor the time for testing it.
4. To create nice interactive tables in order to make them more readable.



<!-- <div class="article-header container featured-image-wrapper mt-4 mb-4" style="max-width: 1200px; max-height: 588px;"> -->
<!--   <iframe src="hhttps://ccamara.github.io/covid_spain/" style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border:0;" allowfullscreen title="YouTube Video"></iframe> -->
<!-- </div> -->

Something here

<div class="featured-image-wrapper">
  <iframe src="https://ccamara.github.io/covid_spain/" style="width: 1200px; height: 600px; border:0;" allowfullscreen title="YouTube Video"></iframe>
</div>


style="max-width: 1200px; max-height: 588px;"

[^lines]: At the time being, the dashboard's source code has 523 lines in two files: one for data gathering and another rmd file with the dashboard.
[^infer]: There is a third scenario: to infer or calculate the data from other datasets.
