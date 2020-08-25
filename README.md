# GSoC Final Report
#### Organization : International Neuroinformatics Coordinating Facility (INCF)
##### Project      : Automated comparison of scientific methods for time series analysis.
##### Student      : Salman Khan
##### Mentors      : Ben Fulcher, Oliver Cliff, Joseph Lizier

### Introduction

In this **Google Summer of Code 2020** project I developed a web-based system that helps the user to compare new time-series analysis algorithms to a collection of over 7700 existing algorithms, implemented as the [_hctsa_ package](https://github.com/benfulcher/hctsa).
The website takes a new time-series analysis algorithm (as python code) from the user and computes its outputs across a [dataset of 1000 diverse time series](https://figshare.com/articles/1000_Empirical_Time_series/5436136).
It then analyzes the correlation between the output of the user's algorithm with the _hctsa_ feature library and presents a range of intuitive output visualizations that show the best-matching features.
This output helps the user to understand connections between their method and the existing interdisciplinary time-series analysis literature, and therefore to assess whether their algorithm is really contributing progress to the literature.

