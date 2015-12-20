# Reproducible Research: Peer Assessment 1
list.of.packages <- c("dplyr", "ggplot2", "knitr")
new.packages <- list.of.packages[!(list.of.packages %in% installed.packages()[,"Package"])]
if(length(new.packages)>0) {install.packages(new.packages)} 
require(dplyr)
require(ggplot2)
require(knitr)
setwd("G://Documents//GitHub//RepData_PeerAssessment1")
## Loading and preprocessing the data

```r
unzip("activity.zip")
rawactivities<-read.csv("activity.csv")
rawactivities$date<-as.Date(rawactivities$date)
str(rawactivities)
```

```
## 'data.frame':	17568 obs. of  3 variables:
##  $ steps   : int  NA NA NA NA NA NA NA NA NA NA ...
##  $ date    : Date, format: "2012-10-01" "2012-10-01" ...
##  $ interval: int  0 5 10 15 20 25 30 35 40 45 ...
```
## What is mean total number of steps taken per day?
For this part of the assignment, you can ignore the missing values in the dataset.

```r
#activities<-filter(rawactivities, complete.cases(rawactivities))
activities<-na.omit(rawactivities)
str(activities)
```

```
## 'data.frame':	15264 obs. of  3 variables:
##  $ steps   : int  0 0 0 0 0 0 0 0 0 0 ...
##  $ date    : Date, format: "2012-10-02" "2012-10-02" ...
##  $ interval: int  0 5 10 15 20 25 30 35 40 45 ...
##  - attr(*, "na.action")=Class 'omit'  Named int [1:2304] 1 2 3 4 5 6 7 8 9 10 ...
##   .. ..- attr(*, "names")= chr [1:2304] "1" "2" "3" "4" ...
```

```r
length(activities$steps)
```

```
## [1] 15264
```
#Calculate the total number of steps taken per day

```r
#stepsperday <- aggregate(steps ~ date, data = activities, FUN = sum)
#length(activities$steps)
```
