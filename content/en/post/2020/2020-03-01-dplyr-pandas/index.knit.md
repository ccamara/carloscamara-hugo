---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Manipulating dataframes in R and Python"
subtitle: "Comparing tidyverse and pandas"
summary: "Some notes for myself"
authors: ["admin"]
tags: ["R", "Python", "dataframe", "pandas", "tidyverse"]
categories: ["Data Science"]
date: 2020-02-08T17:46:34Z
lastmod: 2020-02-01T17:46:34Z
featured: false
draft: true

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false
  placement: 1

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---




## Loading data.

### Loading a CSV file.

#### R


```r
# We will be loading a CSV file from  RamiKrispin's coronavirus' package.
csv_url = "https://raw.githubusercontent.com/RamiKrispin/coronavirus/master/csv/coronavirus.csv"

# Read the CSV, convert it into a dataframe and store it in a variable.
r_df <- read.csv(csv_url)

# Explore the first on the dataframe.
head(coronavirus, 12)
```

```
##    Province.State Country.Region      Lat     Long       date cases      type
## 1                          Japan 35.67620 139.6503 2020-01-22     2 confirmed
## 2                    South Korea 37.56650 126.9780 2020-01-22     1 confirmed
## 3                       Thailand 13.75630 100.5018 2020-01-22     2 confirmed
## 4           Anhui Mainland China 31.82571 117.2264 2020-01-22     1 confirmed
## 5         Beijing Mainland China 40.18238 116.4142 2020-01-22    14 confirmed
## 6       Chongqing Mainland China 30.05718 107.8740 2020-01-22     6 confirmed
## 7          Fujian Mainland China 26.07783 117.9895 2020-01-22     1 confirmed
## 8       Guangdong Mainland China 23.33841 113.4220 2020-01-22    26 confirmed
## 9         Guangxi Mainland China 23.82908 108.7881 2020-01-22     2 confirmed
## 10        Guizhou Mainland China 26.81536 106.8748 2020-01-22     1 confirmed
## 11         Hainan Mainland China 19.19673 109.7455 2020-01-22     4 confirmed
## 12          Hebei Mainland China 38.04280 114.5149 2020-01-22     1 confirmed
```

#### Python


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
##    Province.State Country.Region   Lat  Long        date  cases       type
## 0             NaN    Afghanistan  33.0  65.0  2020-01-22      0  confirmed
## 1             NaN    Afghanistan  33.0  65.0  2020-01-23      0  confirmed
## 2             NaN    Afghanistan  33.0  65.0  2020-01-24      0  confirmed
## 3             NaN    Afghanistan  33.0  65.0  2020-01-25      0  confirmed
## 4             NaN    Afghanistan  33.0  65.0  2020-01-26      0  confirmed
## 5             NaN    Afghanistan  33.0  65.0  2020-01-27      0  confirmed
## 6             NaN    Afghanistan  33.0  65.0  2020-01-28      0  confirmed
## 7             NaN    Afghanistan  33.0  65.0  2020-01-29      0  confirmed
## 8             NaN    Afghanistan  33.0  65.0  2020-01-30      0  confirmed
## 9             NaN    Afghanistan  33.0  65.0  2020-01-31      0  confirmed
## 10            NaN    Afghanistan  33.0  65.0  2020-02-01      0  confirmed
## 11            NaN    Afghanistan  33.0  65.0  2020-02-02      0  confirmed
```

So far, there are no significant differences between both, but note the following differences:
1. `R` works with regular functions, whereas`Python` uses methods instead.
1. In order to work with dataframes in `Python`, `pandas` module has to be imported beforehand, whereas it is a base feature from `R`.
2. Both commands have read the same file but, apparently, they display different data. We will need to explore further the imported data to make sure that both are what we expected and, therefore, the same.


## Exploring a dataframe



### R


```r
# Explore what kind of object r_df is.
str(r_df)
```

```
## 'data.frame':	86240 obs. of  7 variables:
##  $ Province.State: Factor w/ 83 levels "","Alberta","Anguilla",..: 1 1 1 1 1 1 1 1 1 1 ...
##  $ Country.Region: Factor w/ 187 levels "Afghanistan",..: 1 1 1 1 1 1 1 1 1 1 ...
##  $ Lat           : num  33 33 33 33 33 33 33 33 33 33 ...
##  $ Long          : num  65 65 65 65 65 65 65 65 65 65 ...
##  $ date          : Factor w/ 110 levels "2020-01-22","2020-01-23",..: 1 2 3 4 5 6 7 8 9 10 ...
##  $ cases         : int  0 0 0 0 0 0 0 0 0 0 ...
##  $ type          : Factor w/ 3 levels "confirmed","death",..: 1 1 1 1 1 1 1 1 1 1 ...
```

```r
# Basic statistics
summary(r_df)
```

```
##                       Province.State         Country.Region       Lat         
##                              :60830   China         :10890   Min.   :-51.796  
##  Anguilla                    :  330   France        : 3630   1st Qu.:  6.811  
##  Anhui                       :  330   United Kingdom: 3630   Median : 22.300  
##  Aruba                       :  330   Canada        : 3410   Mean   : 20.854  
##  Australian Capital Territory:  330   Australia     : 2640   3rd Qu.: 40.153  
##  Beijing                     :  330   Netherlands   : 1650   Max.   : 71.707  
##  (Other)                     :23760   (Other)       :60390                    
##       Long                 date           cases                  type      
##  Min.   :-135.00   2020-01-22:  784   Min.   :-10034.00   confirmed:29260  
##  1st Qu.: -14.45   2020-01-23:  784   1st Qu.:     0.00   death    :29260  
##  Median :  21.75   2020-01-24:  784   Median :     0.00   recovered:27720  
##  Mean   :  24.28   2020-01-25:  784   Mean   :    67.18                    
##  3rd Qu.:  81.00   2020-01-26:  784   3rd Qu.:     1.00                    
##  Max.   : 178.06   2020-01-27:  784   Max.   : 36188.00                    
##                    (Other)   :81536
```

```r
# Explore unique values within a variable.
levels(r_df$date)
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
```

### Python


```python
# Explore what kind of entity py_df is.
py_df.info()

# Now, calculate basic statistics for the numeric columns in the DataFrame.
```

```
## <class 'pandas.core.frame.DataFrame'>
## RangeIndex: 86240 entries, 0 to 86239
## Data columns (total 7 columns):
##  #   Column          Non-Null Count  Dtype  
## ---  ------          --------------  -----  
##  0   Province.State  25410 non-null  object 
##  1   Country.Region  86240 non-null  object 
##  2   Lat             86240 non-null  float64
##  3   Long            86240 non-null  float64
##  4   date            86240 non-null  object 
##  5   cases           86240 non-null  int64  
##  6   type            86240 non-null  object 
## dtypes: float64(2), int64(1), object(4)
## memory usage: 4.6+ MB
```

```python
py_df.describe()

# List unique values in the df['date'] column
```

```
##                 Lat          Long         cases
## count  86240.000000  86240.000000  86240.000000
## mean      20.853748     24.276041     67.177505
## std       24.599296     69.369005    770.462575
## min      -51.796300   -135.000000 -10034.000000
## 25%        6.810525    -14.452400      0.000000
## 50%       22.300000     21.745300      0.000000
## 75%       40.152925     81.000000      1.000000
## max       71.706900    178.065000  36188.000000
```

```python
py_df['date'].unique()
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
##        '2020-05-09', '2020-05-10'], dtype=object)
```
Note:

We prefer to use this notation in order to prvent problems with columnws with a dot inside.

## Sorting dataframe


```r
library(tidyverse)
```

```
## ── Attaching packages ──────────────────────────────────────────────────────────────────────────────── tidyverse 1.3.0 ──
```

```
## ✓ ggplot2 3.2.1     ✓ purrr   0.3.4
## ✓ tibble  3.0.1     ✓ dplyr   0.8.5
## ✓ tidyr   1.0.0     ✓ stringr 1.4.0
## ✓ readr   1.3.1     ✓ forcats 0.5.0
```

```
## ── Conflicts ─────────────────────────────────────────────────────────────────────────────────── tidyverse_conflicts() ──
## x dplyr::filter() masks stats::filter()
## x dplyr::lag()    masks stats::lag()
```

```r
head(arrange(r_df, Country.Region))
```

```
##   Province.State Country.Region Lat Long       date cases      type
## 1                   Afghanistan  33   65 2020-01-22     0 confirmed
## 2                   Afghanistan  33   65 2020-01-23     0 confirmed
## 3                   Afghanistan  33   65 2020-01-24     0 confirmed
## 4                   Afghanistan  33   65 2020-01-25     0 confirmed
## 5                   Afghanistan  33   65 2020-01-26     0 confirmed
## 6                   Afghanistan  33   65 2020-01-27     0 confirmed
```


```python
py_df.sort_values(['Country.Region']).head()
```

```
##       Province.State Country.Region   Lat  Long        date  cases       type
## 0                NaN    Afghanistan  33.0  65.0  2020-01-22      0  confirmed
## 58550            NaN    Afghanistan  33.0  65.0  2020-02-21      0  recovered
## 58551            NaN    Afghanistan  33.0  65.0  2020-02-22      0  recovered
## 58552            NaN    Afghanistan  33.0  65.0  2020-02-23      0  recovered
## 58553            NaN    Afghanistan  33.0  65.0  2020-02-24      0  recovered
```

## Select and summarise

Let's pretend that we want to have a table displaying the top 10 countries with the most number of confirmed cases until 10th May 2020.

### R


```r
r_df %>% 
  # select(Country.Region, cases, type) %>% 
  filter(type == "confirmed") %>% 
  group_by(Country.Region) %>% 
  summarise(total = sum(cases)) %>% 
  arrange(desc(total)) %>% 
  head(5)
```

```
## # A tibble: 5 x 2
##   Country.Region   total
##   <fct>            <int>
## 1 US             1329260
## 2 Spain           224350
## 3 United Kingdom  220449
## 4 Italy           219070
## 5 Russia          209688
```

```r
# Or, even more succintly:
r_df %>% 
  filter(type == "confirmed") %>% 
  count(Country.Region, wt = cases, sort = TRUE, name = "total") %>% 
  head(5)
```

```
## # A tibble: 5 x 2
##   Country.Region   total
##   <fct>            <int>
## 1 US             1329260
## 2 Spain           224350
## 3 United Kingdom  220449
## 4 Italy           219070
## 5 Russia          209688
```

### Python


```python
py_df.loc[py_df['type'] == 'confirmed'].groupby('Country.Region').agg(
  {'cases':'sum'}
).rename(columns={'cases': 'total'}).sort_values(
  ['total'], ascending = False).head(5)
```

```
##                   total
## Country.Region         
## US              1329260
## Spain            224350
## United Kingdom   220449
## Italy            219070
## Russia           209688
```

## Joins and calculations

But that's not fair, we are comparing countries with very different number of population! If we are to compare them, we need to use relative values. For example, we would need to create a ranking based on the total number of cases per 1000 habitants.



