---
description: Exercises using R and the rerddapXtracto R package
---

# R Tutorial

## About

This document describes R scripts used for demonstrations in the NOAA Satellite Course. The scripts highlight the uses for rerddapXtracto, a R package with functions that allow easy extraction of satellite data from ERDDAP servers. Some of these exercises are also in the rerddapXtracto vignette at [https://cran.r-project.org/web/packages/rerddapXtracto/vignettes/UsingrerddapXtracto.html](https://cran.r-project.org/web/packages/rerddapXtracto/vignettes/UsingrerddapXtracto.html)

## **Software requirements**

### **R and R Studio**

The latest version of [R Studio](https://rstudio.com/) is required to participate in the R tutorials and examples presented in the course.

* [R 4.x ](https://www.r-project.org/) is required for the R packages that will be used in the course.
* [R Script for required modules](https://github.com/CoastWatch-WestCoast/satellite-course-may2021/blob/master/resources/Prerequisites.R): R script to test and/or install required modules for workshop exercises.

## Contents

The source notebook file \(.Rmd\) are available for following along during the course or on your own from our [GitHub repository](https://github.com/CoastWatch-WestCoast/r_code).

**Chapter 1 - Introduction**  
An overview of the main rerddapXtracto functions. 

**Chapter 2 - Extract data within a boundary**  
Visualize data from within the boundaries of the Monterey Bay National Marine Sanctuary and visualize the data in a map.

**Chapter 3 - Matchups to ship or animal tracks**  
Extract satellite data around a set of points defined by longitude, latitude, and time coordinates like that produced by animal telemetry, and ship tracks, or a glider tracts. This function can now handle dataset requests which cross the dateline.

**Chapter 4 - Create and plot timeseries**  
Extract time-series for fours different satellite chlorophyll datasets. Plot the results to examine the similarities and differences among the datasets. This exercise is useful for application that require piecing together a long time series from several separate satellite missions.

**Chapter 5 - Matchup satellite and buoy data**  
Extract SST buoy data from ERDDAP tabular database and then extract the SST satellite data that is coincident with the buoy data.

**Chapter 6 - Define a marine habitat**  
Import SST data and apply a temperature threshold to identify turtle habitats

**Chapter 7 - Reprojecting gridded and tabular data**    
Obtain cruise track data, buoy data, and satellite data from ERDDAP and map all three types of the data on a map in an Alaska Albers projection

**Chapter 8 - Working with Projected Datasets**  
Download projected sea ice data and calculate the indices to use to extract a subset of the projected data. Shows how to create the url to download data directly in R and demonstrates four different ways to map the projected dataset.

