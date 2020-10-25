---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Manipulating dataframes in R and Python"
subtitle: "Comparing tidyverse and pandas"
summary: ""
authors: ["admin"]
tags: ["R", "Python", "dataframe", "pandas", "tidyverse"]
categories: ["Data Science"]
date: 2020-02-08T17:46:34Z
lastmod: 2020-02-01T17:46:34Z
featured: false
draft: false
math: true

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
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

While I have been using `R` for many years now (mainly for data manipulation and visualization), and I am extremely happy with some of its features (like how easy is to deal with data or to create interactive reports that can be exported in plenty of different outputs, such as pdf, documents, slides, dashboards or blog posts like this one). However, I have always wanted to learn `python`, mostly because it is a multi-purpose language that I would be able to use in other aspects of my everyday life such as web development, `QGIS` or Academic research. It is for that reason that I have recently started to learn `python`'s `pandas`.

In the following blog post I will be comparing how to perform the same tasks using `pandas` and `tidyverse`. This mainly serves two learning outcomes:

1.  To generate a cheat sheet that can work as a reminder (for myself): I know there are pages like [this one on `pandas` documentation comparing it to `R`'s syntax](https://pandas.pydata.org/pandas-docs/stable/getting_started/comparison/comparison_with_r.html), but I learn by doing, so I needed to write the code myself)
2.  To use `reticulate` package, which allows running both, `R` and `python` within the same document (a `Rmarkdown` file to be more specific)

## Loading environment

Since I want to use `Python` and `R` from a `.Rmarkdown` file, I first need to load `reticulate` for this, which is a `python` interface for `R`. Also, since `pandas` is not a standard library module, I need to load a python environment[^1] with the required packages. `reticulate` makes it possible to load environments created with `anaconda`.

[^1]: If there is something that I have fallen in love with `python` so far is how convenient and easy are to create virtual environments from a simple `yaml` file listing all the dependencies. This is something that would be very useful in `R`, too and I should explore in the future: I know `packrat` is there for this purpose, but it is not as fast and easy to deal with as `conda` environments. On the other hand, if I am not mistaken, `conda` also has `R` libraries, so it may be possible to create conda environments for R, too.

The last step is to load some data about COVID-19 provided by `coronavirus` package, which I will be using in this blog post.


```r
library(reticulate)
library(DT)
use_condaenv('osm_imports_preparations', required = TRUE)
```

## Loading data

First thing we are doing to do is to read a CSV file and turn it into a dataframe which we are going to manipulate in the next steps.

### R


```r
# We will be loading a CSV file from  RamiKrispin's coronavirus' package.
csv_url = "https://raw.githubusercontent.com/RamiKrispin/coronavirus/master/csv/coronavirus.csv"

# Read the CSV, convert it into a dataframe and store it in a variable.
r_df <- read.csv(csv_url)

# Explore the first on the dataframe.
head(r_df, 12)
```

```
##          date province     country      lat     long      type cases
## 1  2020-01-22          Afghanistan 33.93911 67.70995 confirmed     0
## 2  2020-01-23          Afghanistan 33.93911 67.70995 confirmed     0
## 3  2020-01-24          Afghanistan 33.93911 67.70995 confirmed     0
## 4  2020-01-25          Afghanistan 33.93911 67.70995 confirmed     0
## 5  2020-01-26          Afghanistan 33.93911 67.70995 confirmed     0
## 6  2020-01-27          Afghanistan 33.93911 67.70995 confirmed     0
## 7  2020-01-28          Afghanistan 33.93911 67.70995 confirmed     0
## 8  2020-01-29          Afghanistan 33.93911 67.70995 confirmed     0
## 9  2020-01-30          Afghanistan 33.93911 67.70995 confirmed     0
## 10 2020-01-31          Afghanistan 33.93911 67.70995 confirmed     0
## 11 2020-02-01          Afghanistan 33.93911 67.70995 confirmed     0
## 12 2020-02-02          Afghanistan 33.93911 67.70995 confirmed     0
```

### Python


```python
import pandas as pd

# We will be loading a CSV file from  RamiKrispin's coronavirus' package.
csv_url = "https://raw.githubusercontent.com/RamiKrispin/coronavirus/master/csv/coronavirus.csv"

# Read the CSV, convert it into a dataframe and store it in a variable.
py_df = pd.read_csv(csv_url)

# Explore the first elements on the dataframe.
py_df.head(12)
```

```
##           date province      country       lat       long       type  cases
## 0   2020-01-22      NaN  Afghanistan  33.93911  67.709953  confirmed      0
## 1   2020-01-23      NaN  Afghanistan  33.93911  67.709953  confirmed      0
## 2   2020-01-24      NaN  Afghanistan  33.93911  67.709953  confirmed      0
## 3   2020-01-25      NaN  Afghanistan  33.93911  67.709953  confirmed      0
## 4   2020-01-26      NaN  Afghanistan  33.93911  67.709953  confirmed      0
## 5   2020-01-27      NaN  Afghanistan  33.93911  67.709953  confirmed      0
## 6   2020-01-28      NaN  Afghanistan  33.93911  67.709953  confirmed      0
## 7   2020-01-29      NaN  Afghanistan  33.93911  67.709953  confirmed      0
## 8   2020-01-30      NaN  Afghanistan  33.93911  67.709953  confirmed      0
## 9   2020-01-31      NaN  Afghanistan  33.93911  67.709953  confirmed      0
## 10  2020-02-01      NaN  Afghanistan  33.93911  67.709953  confirmed      0
## 11  2020-02-02      NaN  Afghanistan  33.93911  67.709953  confirmed      0
```

So far, there are no significant differences between both, but note the following differences:

1.  `R` works with regular **functions**, whereas `python` uses **methods** instead.
2.  In order to work with dataframes in `python`, `pandas` module has to be imported beforehand, whereas it is a base feature from `R`.
3.  Both commands have read the same file but, apparently, they display different data. We will need to explore further the imported data to make sure that both are what we expected and, therefore, the same.

## Exploring a dataframe

In this step we are going to evaluate what kind of object have we created, as well as a very basic data exploration.

### R


```r
# Explore what kind of object r_df is.
str(r_df)
```

```
## 'data.frame':	218276 obs. of  7 variables:
##  $ date    : chr  "2020-01-22" "2020-01-23" "2020-01-24" "2020-01-25" ...
##  $ province: chr  "" "" "" "" ...
##  $ country : chr  "Afghanistan" "Afghanistan" "Afghanistan" "Afghanistan" ...
##  $ lat     : num  33.9 33.9 33.9 33.9 33.9 ...
##  $ long    : num  67.7 67.7 67.7 67.7 67.7 ...
##  $ type    : chr  "confirmed" "confirmed" "confirmed" "confirmed" ...
##  $ cases   : int  0 0 0 0 0 0 0 0 0 0 ...
```

```r
# Basic statistics
summary(r_df)
```

```
##      date             province           country               lat         
##  Length:218276      Length:218276      Length:218276      Min.   :-51.796  
##  Class :character   Class :character   Class :character   1st Qu.:  6.428  
##  Mode  :character   Mode  :character   Mode  :character   Median : 22.041  
##                                                           Mean   : 20.561  
##                                                           3rd Qu.: 40.182  
##                                                           Max.   : 71.707  
##       long             type               cases         
##  Min.   :-135.00   Length:218276      Min.   :-16298.0  
##  1st Qu.: -12.89   Class :character   1st Qu.:     0.0  
##  Median :  21.75   Mode  :character   Median :     0.0  
##  Mean   :  25.01                      Mean   :   331.8  
##  3rd Qu.:  84.25                      3rd Qu.:    12.0  
##  Max.   : 178.06                      Max.   :140050.0
```

```r
# Explore unique values within a variable.
levels(as.factor(r_df$date))
```

```
##   [1] "2020-01-22" "2020-01-23" "2020-01-24" "2020-01-25" "2020-01-26"
##   [6] "2020-01-27" "2020-01-28" "2020-01-29" "2020-01-30" "2020-01-31"
##  [11] "2020-02-01" "2020-02-02" "2020-02-03" "2020-02-04" "2020-02-05"
##  [16] "2020-02-06" "2020-02-07" "2020-02-08" "2020-02-09" "2020-02-10"
##  [21] "2020-02-11" "2020-02-12" "2020-02-13" "2020-02-14" "2020-02-15"
##  [26] "2020-02-16" "2020-02-17" "2020-02-18" "2020-02-19" "2020-02-20"
##  [31] "2020-02-21" "2020-02-22" "2020-02-23" "2020-02-24" "2020-02-25"
##  [36] "2020-02-26" "2020-02-27" "2020-02-28" "2020-02-29" "2020-03-01"
##  [41] "2020-03-02" "2020-03-03" "2020-03-04" "2020-03-05" "2020-03-06"
##  [46] "2020-03-07" "2020-03-08" "2020-03-09" "2020-03-10" "2020-03-11"
##  [51] "2020-03-12" "2020-03-13" "2020-03-14" "2020-03-15" "2020-03-16"
##  [56] "2020-03-17" "2020-03-18" "2020-03-19" "2020-03-20" "2020-03-21"
##  [61] "2020-03-22" "2020-03-23" "2020-03-24" "2020-03-25" "2020-03-26"
##  [66] "2020-03-27" "2020-03-28" "2020-03-29" "2020-03-30" "2020-03-31"
##  [71] "2020-04-01" "2020-04-02" "2020-04-03" "2020-04-04" "2020-04-05"
##  [76] "2020-04-06" "2020-04-07" "2020-04-08" "2020-04-09" "2020-04-10"
##  [81] "2020-04-11" "2020-04-12" "2020-04-13" "2020-04-14" "2020-04-15"
##  [86] "2020-04-16" "2020-04-17" "2020-04-18" "2020-04-19" "2020-04-20"
##  [91] "2020-04-21" "2020-04-22" "2020-04-23" "2020-04-24" "2020-04-25"
##  [96] "2020-04-26" "2020-04-27" "2020-04-28" "2020-04-29" "2020-04-30"
## [101] "2020-05-01" "2020-05-02" "2020-05-03" "2020-05-04" "2020-05-05"
## [106] "2020-05-06" "2020-05-07" "2020-05-08" "2020-05-09" "2020-05-10"
## [111] "2020-05-11" "2020-05-12" "2020-05-13" "2020-05-14" "2020-05-15"
## [116] "2020-05-16" "2020-05-17" "2020-05-18" "2020-05-19" "2020-05-20"
## [121] "2020-05-21" "2020-05-22" "2020-05-23" "2020-05-24" "2020-05-25"
## [126] "2020-05-26" "2020-05-27" "2020-05-28" "2020-05-29" "2020-05-30"
## [131] "2020-05-31" "2020-06-01" "2020-06-02" "2020-06-03" "2020-06-04"
## [136] "2020-06-05" "2020-06-06" "2020-06-07" "2020-06-08" "2020-06-09"
## [141] "2020-06-10" "2020-06-11" "2020-06-12" "2020-06-13" "2020-06-14"
## [146] "2020-06-15" "2020-06-16" "2020-06-17" "2020-06-18" "2020-06-19"
## [151] "2020-06-20" "2020-06-21" "2020-06-22" "2020-06-23" "2020-06-24"
## [156] "2020-06-25" "2020-06-26" "2020-06-27" "2020-06-28" "2020-06-29"
## [161] "2020-06-30" "2020-07-01" "2020-07-02" "2020-07-03" "2020-07-04"
## [166] "2020-07-05" "2020-07-06" "2020-07-07" "2020-07-08" "2020-07-09"
## [171] "2020-07-10" "2020-07-11" "2020-07-12" "2020-07-13" "2020-07-14"
## [176] "2020-07-15" "2020-07-16" "2020-07-17" "2020-07-18" "2020-07-19"
## [181] "2020-07-20" "2020-07-21" "2020-07-22" "2020-07-23" "2020-07-24"
## [186] "2020-07-25" "2020-07-26" "2020-07-27" "2020-07-28" "2020-07-29"
## [191] "2020-07-30" "2020-07-31" "2020-08-01" "2020-08-02" "2020-08-03"
## [196] "2020-08-04" "2020-08-05" "2020-08-06" "2020-08-07" "2020-08-08"
## [201] "2020-08-09" "2020-08-10" "2020-08-11" "2020-08-12" "2020-08-13"
## [206] "2020-08-14" "2020-08-15" "2020-08-16" "2020-08-17" "2020-08-18"
## [211] "2020-08-19" "2020-08-20" "2020-08-21" "2020-08-22" "2020-08-23"
## [216] "2020-08-24" "2020-08-25" "2020-08-26" "2020-08-27" "2020-08-28"
## [221] "2020-08-29" "2020-08-30" "2020-08-31" "2020-09-01" "2020-09-02"
## [226] "2020-09-03" "2020-09-04" "2020-09-05" "2020-09-06" "2020-09-07"
## [231] "2020-09-08" "2020-09-09" "2020-09-10" "2020-09-11" "2020-09-12"
## [236] "2020-09-13" "2020-09-14" "2020-09-15" "2020-09-16" "2020-09-17"
## [241] "2020-09-18" "2020-09-19" "2020-09-20" "2020-09-21" "2020-09-22"
## [246] "2020-09-23" "2020-09-24" "2020-09-25" "2020-09-26" "2020-09-27"
## [251] "2020-09-28" "2020-09-29" "2020-09-30" "2020-10-01" "2020-10-02"
## [256] "2020-10-03" "2020-10-04" "2020-10-05" "2020-10-06" "2020-10-07"
## [261] "2020-10-08" "2020-10-09" "2020-10-10" "2020-10-11" "2020-10-12"
## [266] "2020-10-13" "2020-10-14" "2020-10-15" "2020-10-16" "2020-10-17"
## [271] "2020-10-18" "2020-10-19" "2020-10-20" "2020-10-21" "2020-10-22"
## [276] "2020-10-23" "2020-10-24"
```

### Python


```python
# Explore what kind of entity py_df is.
py_df.info()

# Now, calculate basic statistics for the numeric columns in the DataFrame.
```

```
## <class 'pandas.core.frame.DataFrame'>
## RangeIndex: 218276 entries, 0 to 218275
## Data columns (total 7 columns):
##  #   Column    Non-Null Count   Dtype  
## ---  ------    --------------   -----  
##  0   date      218276 non-null  object 
##  1   province  63433 non-null   object 
##  2   country   218276 non-null  object 
##  3   lat       218276 non-null  float64
##  4   long      218276 non-null  float64
##  5   type      218276 non-null  object 
##  6   cases     218276 non-null  int64  
## dtypes: float64(2), int64(1), object(4)
## memory usage: 11.7+ MB
```

```python
py_df.describe()

# List unique values in the df['date'] column
```

```
##                  lat           long          cases
## count  218276.000000  218276.000000  218276.000000
## mean       20.561062      25.011408     331.749812
## std        24.759252      69.572388    3045.547043
## min       -51.796300    -135.000000  -16298.000000
## 25%         6.428055     -12.885800       0.000000
## 50%        22.041450      21.745300       0.000000
## 75%        40.182400      84.250000      12.000000
## max        71.706900     178.065000  140050.000000
```

```python
py_df['date'].unique() # I prefer using this notation to prevent problems with columns with a dot inside.
```

```
## array(['2020-01-22', '2020-01-23', '2020-01-24', '2020-01-25',
##        '2020-01-26', '2020-01-27', '2020-01-28', '2020-01-29',
##        '2020-01-30', '2020-01-31', '2020-02-01', '2020-02-02',
##        '2020-02-03', '2020-02-04', '2020-02-05', '2020-02-06',
##        '2020-02-07', '2020-02-08', '2020-02-09', '2020-02-10',
##        '2020-02-11', '2020-02-12', '2020-02-13', '2020-02-14',
##        '2020-02-15', '2020-02-16', '2020-02-17', '2020-02-18',
##        '2020-02-19', '2020-02-20', '2020-02-21', '2020-02-22',
##        '2020-02-23', '2020-02-24', '2020-02-25', '2020-02-26',
##        '2020-02-27', '2020-02-28', '2020-02-29', '2020-03-01',
##        '2020-03-02', '2020-03-03', '2020-03-04', '2020-03-05',
##        '2020-03-06', '2020-03-07', '2020-03-08', '2020-03-09',
##        '2020-03-10', '2020-03-11', '2020-03-12', '2020-03-13',
##        '2020-03-14', '2020-03-15', '2020-03-16', '2020-03-17',
##        '2020-03-18', '2020-03-19', '2020-03-20', '2020-03-21',
##        '2020-03-22', '2020-03-23', '2020-03-24', '2020-03-25',
##        '2020-03-26', '2020-03-27', '2020-03-28', '2020-03-29',
##        '2020-03-30', '2020-03-31', '2020-04-01', '2020-04-02',
##        '2020-04-03', '2020-04-04', '2020-04-05', '2020-04-06',
##        '2020-04-07', '2020-04-08', '2020-04-09', '2020-04-10',
##        '2020-04-11', '2020-04-12', '2020-04-13', '2020-04-14',
##        '2020-04-15', '2020-04-16', '2020-04-17', '2020-04-18',
##        '2020-04-19', '2020-04-20', '2020-04-21', '2020-04-22',
##        '2020-04-23', '2020-04-24', '2020-04-25', '2020-04-26',
##        '2020-04-27', '2020-04-28', '2020-04-29', '2020-04-30',
##        '2020-05-01', '2020-05-02', '2020-05-03', '2020-05-04',
##        '2020-05-05', '2020-05-06', '2020-05-07', '2020-05-08',
##        '2020-05-09', '2020-05-10', '2020-05-11', '2020-05-12',
##        '2020-05-13', '2020-05-14', '2020-05-15', '2020-05-16',
##        '2020-05-17', '2020-05-18', '2020-05-19', '2020-05-20',
##        '2020-05-21', '2020-05-22', '2020-05-23', '2020-05-24',
##        '2020-05-25', '2020-05-26', '2020-05-27', '2020-05-28',
##        '2020-05-29', '2020-05-30', '2020-05-31', '2020-06-01',
##        '2020-06-02', '2020-06-03', '2020-06-04', '2020-06-05',
##        '2020-06-06', '2020-06-07', '2020-06-08', '2020-06-09',
##        '2020-06-10', '2020-06-11', '2020-06-12', '2020-06-13',
##        '2020-06-14', '2020-06-15', '2020-06-16', '2020-06-17',
##        '2020-06-18', '2020-06-19', '2020-06-20', '2020-06-21',
##        '2020-06-22', '2020-06-23', '2020-06-24', '2020-06-25',
##        '2020-06-26', '2020-06-27', '2020-06-28', '2020-06-29',
##        '2020-06-30', '2020-07-01', '2020-07-02', '2020-07-03',
##        '2020-07-04', '2020-07-05', '2020-07-06', '2020-07-07',
##        '2020-07-08', '2020-07-09', '2020-07-10', '2020-07-11',
##        '2020-07-12', '2020-07-13', '2020-07-14', '2020-07-15',
##        '2020-07-16', '2020-07-17', '2020-07-18', '2020-07-19',
##        '2020-07-20', '2020-07-21', '2020-07-22', '2020-07-23',
##        '2020-07-24', '2020-07-25', '2020-07-26', '2020-07-27',
##        '2020-07-28', '2020-07-29', '2020-07-30', '2020-07-31',
##        '2020-08-01', '2020-08-02', '2020-08-03', '2020-08-04',
##        '2020-08-05', '2020-08-06', '2020-08-07', '2020-08-08',
##        '2020-08-09', '2020-08-10', '2020-08-11', '2020-08-12',
##        '2020-08-13', '2020-08-14', '2020-08-15', '2020-08-16',
##        '2020-08-17', '2020-08-18', '2020-08-19', '2020-08-20',
##        '2020-08-21', '2020-08-22', '2020-08-23', '2020-08-24',
##        '2020-08-25', '2020-08-26', '2020-08-27', '2020-08-28',
##        '2020-08-29', '2020-08-30', '2020-08-31', '2020-09-01',
##        '2020-09-02', '2020-09-03', '2020-09-04', '2020-09-05',
##        '2020-09-06', '2020-09-07', '2020-09-08', '2020-09-09',
##        '2020-09-10', '2020-09-11', '2020-09-12', '2020-09-13',
##        '2020-09-14', '2020-09-15', '2020-09-16', '2020-09-17',
##        '2020-09-18', '2020-09-19', '2020-09-20', '2020-09-21',
##        '2020-09-22', '2020-09-23', '2020-09-24', '2020-09-25',
##        '2020-09-26', '2020-09-27', '2020-09-28', '2020-09-29',
##        '2020-09-30', '2020-10-01', '2020-10-02', '2020-10-03',
##        '2020-10-04', '2020-10-05', '2020-10-06', '2020-10-07',
##        '2020-10-08', '2020-10-09', '2020-10-10', '2020-10-11',
##        '2020-10-12', '2020-10-13', '2020-10-14', '2020-10-15',
##        '2020-10-16', '2020-10-17', '2020-10-18', '2020-10-19',
##        '2020-10-20', '2020-10-21', '2020-10-22', '2020-10-23',
##        '2020-10-24'], dtype=object)
```

There are no significant differences, nor in the syntax nor in the ouput.

Note:

We prefer to use this notation in order to prevent problems with columns with a dot inside.

## Sorting dataframe


```r
library(tidyverse)
```

```
## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.0 ──
```

```
## ✓ ggplot2 3.3.2     ✓ purrr   0.3.4
## ✓ tibble  3.0.4     ✓ dplyr   1.0.2
## ✓ tidyr   1.1.2     ✓ stringr 1.4.0
## ✓ readr   1.3.1     ✓ forcats 0.5.0
```

```
## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
## x dplyr::filter() masks stats::filter()
## x dplyr::lag()    masks stats::lag()
```

```r
head(arrange(r_df, country))
```

```
##         date province     country      lat     long      type cases
## 1 2020-01-22          Afghanistan 33.93911 67.70995 confirmed     0
## 2 2020-01-23          Afghanistan 33.93911 67.70995 confirmed     0
## 3 2020-01-24          Afghanistan 33.93911 67.70995 confirmed     0
## 4 2020-01-25          Afghanistan 33.93911 67.70995 confirmed     0
## 5 2020-01-26          Afghanistan 33.93911 67.70995 confirmed     0
## 6 2020-01-27          Afghanistan 33.93911 67.70995 confirmed     0
```


```python
py_df.sort_values(['country']).head()
```

```
##               date province      country       lat       long       type  cases
## 0       2020-01-22      NaN  Afghanistan  33.93911  67.709953  confirmed      0
## 147922  2020-01-26      NaN  Afghanistan  33.93911  67.709953  recovered      0
## 147921  2020-01-25      NaN  Afghanistan  33.93911  67.709953  recovered      0
## 147920  2020-01-24      NaN  Afghanistan  33.93911  67.709953  recovered      0
## 147919  2020-01-23      NaN  Afghanistan  33.93911  67.709953  recovered      0
```

## Select and summarise

Let's pretend that we want to have a table displaying the top 10 countries with the most number of confirmed cases until today (2020-10-25).

### R


```r
r_df %>% 
  # select(Country.Region, cases, type) %>% 
  filter(type == "confirmed") %>% 
  group_by(country) %>% 
  summarise(total = sum(cases)) %>% 
  arrange(desc(total)) %>% 
  head(5)
```

```
## # A tibble: 5 x 2
##   country   total
##   <chr>     <int>
## 1 US      8575177
## 2 India   7814682
## 3 Brazil  5380635
## 4 Russia  1487260
## 5 France  1084659
```

```r
# Or, even more succintly:
r_df %>% 
  filter(type == "confirmed") %>% 
  count(country, wt = cases, sort = TRUE, name = "total") %>% 
  head(5)
```

```
##   country   total
## 1      US 8575177
## 2   India 7814682
## 3  Brazil 5380635
## 4  Russia 1487260
## 5  France 1084659
```

### Python


```python
py_df.loc[py_df['type'] == 'confirmed'].groupby('country').agg(
  {'cases':'sum'}
).rename(columns={'cases': 'total'}).sort_values(
  ['total'], ascending = False).head(5)
```

```
##            total
## country         
## US       8575177
## India    7814682
## Brazil   5380635
## Russia   1487260
## France   1084659
```

This is something funny. `python` takes pride in stating that is an elegant and easy to read syntax due to its strict indentation syntax. On the other hand, I have met several `python` proponents mocking about `R`'s code to be quite obscure and difficult to memorise. While I often share the same views (especially when dealing with base `R`'s syntax), I particularly find `tidypverse`'s syntax far easier to read and memorise than `pandas`' . While the first makes use of the pipe operator ( `%>%`) to chain commands while preventing typing unnecessary data, the latter requires to concatenate up to six different methods in a single line, which becomes too long to read (and thus, not liked very much by [python's guidelines PEP8](https://www.python.org/dev/peps/pep-0008/#maximum-line-length))

## Joins and calculations

But that's not fair, we are comparing countries with very different number of population! If we are to compare them, we need to use relative values. For example, we would need to create a ranking based on the total number of cases per 1000 habitants.

In order to do so, we will need to do the following steps:

1.  Load a dataframe with population data per each country
2.  Add the population data by join our existing dataframes with the newly created one in the previous step (left join)
3.  Calculate relative number of confirmed cases like this: `\(confirmed~rel = \frac{confirmed}{population}\)`

### R


```r
# Load population data.
countries19 <- read.csv("data/countries_pop19.csv")

r_df %>% 
  filter(type == "confirmed") %>% 
  count(country, wt = cases, sort = TRUE, name = "confirmed") %>% 
  # Add population column.
  left_join(countries19, by = c("country" = "Location")) %>% 
  # Calculate relative cases.
  mutate(confirmed_rel = confirmed / PopTotal) %>% 
  # Select certain columns only.
  select(country, confirmed, confirmed_rel) %>% 
  # Sort by confirmed_rel on descending order.
  arrange(desc(confirmed_rel)) %>% 
  # Display everything on a nice datatable.
  head(10)
```

```
##       country confirmed confirmed_rel
## 1     Andorra      4038      52.34231
## 2     Bahrain     79975      48.73066
## 3       Qatar    130965      46.24354
## 4      Israel    309413      36.31875
## 5    Holy See        27      33.12883
## 6      Panama    128515      30.26417
## 7      Kuwait    120927      28.74371
## 8        Peru    883116      27.16406
## 9  Montenegro     16629      26.47981
## 10    Belgium    305409      26.46680
```

### Python


```python

# Load population data.
countries19 = pd.read_csv('data/countries_pop19.csv')

py_confirmed_rel = py_df.loc[py_df['type'] == 'confirmed'].groupby('country').agg(
  {'cases':'sum'}
).rename(columns={'cases': 'confirmed'})

# Join population information.
py_confirmed_rel = py_confirmed_rel.join(countries19.set_index('Location'), on = 'country')

# Calculate relative confirmed cases.
py_confirmed_rel = py_confirmed_rel.assign(confirmed_rel = py_confirmed_rel['confirmed']/py_confirmed_rel['PopTotal'])

py_confirmed_rel = py_confirmed_rel[['confirmed', 'confirmed_rel']]

py_confirmed_rel.sort_values(['confirmed_rel'], ascending = False).head(10)
```

```
##             confirmed  confirmed_rel
## country                             
## Andorra          4038      52.342312
## Bahrain         79975      48.730657
## Qatar          130965      46.243544
## Israel         309413      36.318753
## Holy See           27      33.128834
## Panama         128515      30.264174
## Kuwait         120927      28.743710
## Peru           883116      27.164056
## Montenegro      16629      26.479805
## Belgium        305409      26.466797
```

## Conclusion

Before concluding, I have to admit that I have been using `tidyverse` for several years, and I am very used to its syntax. Therefore, it is no wonder that I feel much more comfortable with it than with `pandas`' . Being said that, I find the latter to be quite straightforward and relatively easy to use and memorise (I will need to check this post and [this page](https://pandas.pydata.org/pandas-docs/stable/getting_started/comparison/comparison_with_r.html) for reference). However, I have two main concerns about pandas:

1.  Compared to `R`, which is more succinct, pandas requires to type many times the data frame's name. This makes it more prone-error and slow to type, but also more difficult to read. If you want to avoid typing it as much, you need to chain a number of methods that result in very long lines, which makes it difficult to comment and it is, again, more difficult to read.
2.  I find it somewhat overwhelming that there are many ways to perform same task in `pandas`. I believe Ted Petrou's advice on learning the [minimum sufficient pandas' syntax](https://medium.com/dunder-data/minimally-sufficient-pandas-a8e67f2a2428) is a good advice, as it makes things simpler.
3.  I miss the magritte's pipe operator, but I guess I should change my mindset when using python.

Regarding `reticulate`: I think it is very promising. While `jupyter notebooks` can be used with different kernels such as `Julia`, `python` or `R` (hence its name), there is no way to combine different kernels in the same notebook, at least that I am aware of. This means that only one language per notebook can be used. On the other hand, reticulate allows you to use different languages within the same document (a markdown file, which I prefer it over jupyter notebooks, by the way). Admittedly, I do not know if that is a common scenario, but it has proven to be very useful for a post like this one.

Being said that, I admit that I expected that I could use one variable from `python` and use it in `R`, if that makes any sense at all. However, that's not possible, as both languages are isolated, which I assume is the logical way (I assume is not straightforward at all to convert from one `python` `list` to an `R` `vector`, for example).
