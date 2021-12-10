---
title: "Final Project"
author: "Valerie Wilson"
date: "12/09/2021"
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(warning = FALSE, message = FALSE)
library("tidyverse")
library(ggplot2)
vgsales<- read.csv("vgsales.csv")
```

# Motivation

There are a huge number of different genres within the video game world; shooters, role-playing, platformers, fighting, etc. Are the same genres universally popular, or do different countries prefer different types of games? The purpose of my analysis is to assess how the popularity of a video game genre varies by region.


# Data Process

The data comes from a web scrape of vgchartz.com and includes 16,598 video game sales. Only games with sales greater than 100,000 copies are included. I will be looking at the popularity of genres in five regions; North America, European Union, Japan, Other (remainder of the world), and Global.

I have eliminated three columns from the original data (Platform, Year, Publisher) because they were not relevant to my research.

I have kept eight variables from the original dataset: Rank, Name, Genre, NA_Sales, EU_Sales, JP_Sales, Other_Sales, Global_Sales.

My initial observation of the data is that the top selling games in Japan are heavily role-playing games while the top selling games in the US and EU are much more of a mix of all genre types.

Source: Smith, G. (2016). Video Game Sales [Data set]. https://www.kaggle.com/gregorut/videogamesales.

# Visualizations

I have produced five bar plots, one plot for each region. Globally, 'Action' and 'Sports' are the two most popular genres. North America, Europe, and other countries show similar results to the global results. Japan shows a drastic difference in favoring the 'Role-Playing' genre.

```{r}

Gl<- ggplot(vgsales, aes(x=Genre, y=Global_Sales)) + 
  geom_bar(stat="identity", fill="pink1") + 
  ggtitle("Global") + 
  ylab("Sales (Million)")+
  theme(axis.text.x = element_text(angle = 90, vjust = 0.5, hjust=1))
Gl + theme(
plot.title = element_text(color="pink3", size=18, face="bold"),
axis.title.x = element_text(color="black", size=12),
axis.title.y = element_text(color="black", size=12)
)

NoA<- ggplot(vgsales, aes(x=Genre, y=NA_Sales)) + 
  geom_bar(stat="identity", fill="cadetblue3") + 
  ggtitle("North America") + 
  ylab("Sales (Million)")+
  theme(axis.text.x = element_text(angle = 90, vjust = 0.5, hjust=1))
NoA + theme(
plot.title = element_text(color="cadetblue4", size=18, face="bold"),
axis.title.x = element_text(color="black", size=12),
axis.title.y = element_text(color="black", size=12)
)

EU<- ggplot(vgsales, aes(x=Genre, y=EU_Sales)) + 
  geom_bar(stat="identity", fill="cadetblue3") + 
  ggtitle("European Union") + 
  ylab("Sales (Million)")+
  theme(axis.text.x = element_text(angle = 90, vjust = 0.5, hjust=1))
EU + theme(
plot.title = element_text(color="cadetblue4", size=18, face="bold"),
axis.title.x = element_text(color="black", size=12),
axis.title.y = element_text(color="black", size=12)
)

JP<- ggplot(vgsales, aes(x=Genre, y=JP_Sales)) + 
  geom_bar(stat="identity", fill="cadetblue3") + 
  ggtitle("Japan") + 
  ylab("Sales (Million)")+
  theme(axis.text.x = element_text(angle = 90, vjust = 0.5, hjust=1))
JP + theme(
plot.title = element_text(color="cadetblue4", size=18, face="bold"),
axis.title.x = element_text(color="black", size=12),
axis.title.y = element_text(color="black", size=12)
)

O<- ggplot(vgsales, aes(x=Genre, y=Other_Sales)) + 
  geom_bar(stat="identity", fill="cadetblue3") + 
  ggtitle("Other") + 
  ylab("Sales (Million)")+
  theme(axis.text.x = element_text(angle = 90, vjust = 0.5, hjust=1))
O + theme(
plot.title = element_text(color="cadetblue4", size=18, face="bold"),
axis.title.x = element_text(color="black", size=12),
axis.title.y = element_text(color="black", size=12)
)
```
