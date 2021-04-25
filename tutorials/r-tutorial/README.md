---
description: Exercises using R and the rerddapXtracto R package
---

# R Tutorial

## Exercise book contents

This document describes R scripts used for demonstrations in the NOAA Satellite Course. The scripts highlight the uses for rerddapXtracto, a R package with functions that allow easy extraction of satellite data from ERDDAP servers. Some of these exercies are also in the rerddapXtracto vignette at [https://cran.r-project.org/web/packages/rerddapXtracto/vignettes/UsingrerddapXtracto.html](https://cran.r-project.org/web/packages/rerddapXtracto/vignettes/UsingrerddapXtracto.html)

This chapter will provide an overview of the main rerddapXtracto functions. Please review the information presented here before moving on to the other chapters.

The remaining chapters each contain a separate demonstration. The demonstrations are HTML or PDF versions of R notebooks. The source notebook file \(.Rmd\) are available for following along during the course or on your own from our [GitHub repository](https://github.com/CoastWatch-WestCoast/r_code).

**Chapter 2: Extract data within a boundary**  
 Visualize data from within the boundaries of the Monterey Bay National Marine Sanctuary and visualize the data in a map.

**Chapter 3 - Matchups to ship or animal tracks**  
 Extract satellite data around a set of points defined by longitude, latitude, and time coordinates like that produced by an animal telemetry tag, and ship track, or a glider tract. This function can now handle dataset requests which cross the dateline.

**Chapter 4 - Create and plot timeseries**  
 Extract a time-series of monthly satellite chlorophyll data for the period of 1997-present from four different monthly satellite datasets. Plot the results to examine the similarities and differences among the datasets. This exercise is useful for application that require piecing together a long time series from several separate satellite missions.

**Chapter 5 - Matchup satellite and buoy data**  
Extract SST buoy data from ERDDAP tabular database and then extract the SST satellite data that is coincident with the buoy data.

**Chapter 6 - Define a marine habitat**  
 Import SST data and apply a temperature threshold to identify turtle habitats

**Chapter 7 - Reprojecting gridded and tabular data**

**Chapter 8 - Working with Projected Datasets**  
Down the grid for a projected sea ice dataset \(coordinates are given in m from the projection point\) and calculate the indices to use to extract a subset of the projected data. Shows how to create the url to download data directly in R, i.e. does not use the `rerddap` or `rerddapXtracto` functions. Gives 4 different examples of ways to map this projected dataset.

