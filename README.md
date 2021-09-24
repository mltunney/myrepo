# Homework1
I can't get my homework to get onto github

---
title: "hw 1"
author: "Maya Tunney"
date: "9/23/2021"
output: html_document
---
```{r}
library(tidyverse)
library(ggplot2)
library(textreadr)
```


## Problem 1

```{r}
bridges<-read.csv("bridges.csv")
```
```{r}
bridges_limited<-select(bridges, "STRUCTURE_NUMBER_008", "STATE_CODE_001", contains("_COND_"), "YEAR_BUILT_027", "ADT_029", "YEAR_ADT_030")
head(bridges_limited)
```

```{r}
since_2015<-filter(bridges_limited, ADT_029>=2015)

ggplot(since_2015, aes(ADT_029))+
  geom_histogram(bins=50, color="blue", fill="light blue")+
  ggtitle("Average Daily Bridge Traffic Since 2015")+
  xlab("Average Daily Traffic (cars)")
```


## Professors

```{r}
faculty_og<- read_html("/Users/mayatunney/Desktop/stat 433/hw1/faculty.html")
faculty<- tail(faculty_og, -58)
head(faculty)
```
