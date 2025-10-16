# exam
---
title: "BambaExam1"
author: "Bamba"
date: "2025-10-16"
output:
  html_document: default
  pdf_document: default
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

## R Markdown

This is an R Markdown document. Markdown is a simple formatting syntax for authoring HTML, PDF, and MS Word documents. For more details on using R Markdown see <http://rmarkdown.rstudio.com>.

When you click the **Knit** button a document will be generated that includes both content as well as the output of any embedded R code chunks within the document. You can embed an R code chunk like this:

```{r cars}
summary(cars)
```

## Including Plots

You can also embed plots, for example:

```{r pressure, echo=FALSE}
library(ggplot2)
library(viridis)
library(dplyr)
library(knitr)

attach(d_HHP2020_24)

summary(d_HHP2020_24)


# Separate the data between has college degree and do not have college degree:
d_HHP2020_24$Education <- ifelse(d_HHP2020_24$Education == "lt hs" + "some hs" + "high school" , 1, 0)
filtered_data <- d_HHP2020_24 %>% filter(
    !is.na(Education) & 
    Education >= 1 & 
    Education <= 2 
  )


summary(filtered_data)
colldeg <- 1  
no_coll <- 0


filtered_data <- d_HHP2020_24 %>% 
  filter(!is.na(Education) & 
         Education >= no_colldeg & 
         Education <= colldeg)

table(d_HHP2020_24$Education)

filtered_data <- d_HHP2020_24 %>% 
  filter(!is.na(Education)) %>%
  mutate(
    college_degree = case_when(
      Education >= 3 ~ 5,  
      Education <= 1 ~ 2,  
       TRUE ~ NA_real_
    )
  ) %>%
  filter(!is.na(colldeg_value))

summary(filtered_data)


filtered_data <- d_HHP2020_24 %>% 
  filter(!is.na(Education) & 
         Education %in% c(1,2, 3, 4,5))

education_summary <- d_HHP2020_24 %>%
  group_by(Education) %>%
  summarise(count = n()) %>%
  arrange(Education)

filtered_data <- d_HHP2020_24 %>%
  filter(!is.na(Education) & !is.na(down)) %>%
  mutate(
    colldeg = ifelse(Education >= 3, 4, 5)  
  )

table(filtered_data$colldeg)

print(education_summary)

summary(education_summary)


filtered_data1 <- d_HHP2020_24 %>%
  filter(!is.na(Education) & !is.na(down)) %>%
  mutate(
    has_college_degree = ifelse(Education >= 3, 4, 5)  
    

summary(filtered_data1)

# Split data
colldeg <- d_HHP2020_24$DOWN[d_HHP2020_24$Education == 1]
no_colldeg <- d_HHP2020_24$DOWN[d_HHP2020_24$Education == 0]

summary(colldeg)


summary(d_HHP2020_24$Education)



```
