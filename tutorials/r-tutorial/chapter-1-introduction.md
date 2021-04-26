---
description: In introduction to the rerddapXtracto R package
---

# Chapter 1 RerddapXtracto

##  RerddapXtracto R package

The “rerddapXtracto” package contains routines to simplify data extraction using ERD’s ERDDAP web service. The “rerddapXtracto”" package subsets and extracts satellite and other oceanographic related data from any ERDDAP server using the R package “rerddap” developed by Scott Chamberlain and the people at rOpenSci \([https://ropensci.org/](https://ropensci.org/)\).

The following is a description of the main functions of the “rerddapXtracto”" package plus key functions from the “rerddap” package that are dependencies for the “rerddapXtracto” functions.

###  rxtracto function

**Summary**  
Extracts environmental data from an ERDDAP server along a x,y,\[z\], and time trajectory, e.g. an animal or cruise track. The script allows you to control the size if a the box \[cube\] surrounding the x,y \[z\] point to be used to determine means and statistics. You can also control from which ERDDAP you pull data from.

**Function**  
 rxtracto &lt;- function\(dataInfo, parameter = NULL, xcoord = NULL, ycoord = NULL, zcoord = NULL, tcoord = NULL, xlen = 0., ylen = 0., zlen = 0., xName = ‘longitude’, yName = ‘latitude’, zName = ‘altitude’, tName = ‘time’, urlbase = ‘[https://coastwatch.pfeg.noaa.gov/erddap](https://coastwatch.pfeg.noaa.gov/erddap)’, verbose = FALSE\)

**Arguments**

* **dataInfo**  The return from an rerddap “info” call to an ERDDAP server
* **parameter**  A character string containing the name of the parameter to extract
* **xcoord**  A comma separated array \(list\) of numbers containing the x-coordinates of the trajectory \(if longitude in \#’ decimal degrees East, either 0-360 or -180 to 180\)
* **ycoord**  A comma separated array \(list\) of numbers containing the y-coordinate of the trajectory \(if latitude in decimal degrees N; -90 to 90\)
* **zcoord**  A comma separated array \(list\) of numbers containing the z-coordinate of the trajectory \(usually altitude or depth\)
* **tcoord**  A comma separated array \(list\) of character strings in the format “YYYY-MM-DD” with the times of the trajectory in “YYYY-MM-DD” \(for now restricted to be time\).
* **xlen**  A comma separated array \(list\) of numbers defining the longitude box around the given point \(xlen/2 around the point\)
* **ylen**  A comma separated array \(list\) of numbers defining the latitude box around the given point \(ylen/2 around the point\)
* **zlen**  A comma separated array \(list\) of numbers defining the depth or altitude box around the given point \(zlen/2 around the point\)
* **xName**  A character string with name of the xcoord in the ERDDAP dataset \(default “longitude”\)
* **yName**  A character string with name of the ycoord in the ERDDAP dataset \(default “latitude”\)
* **zName**  A character string with name of the zcoord in the ERDDAP dataset \(default “altitude”\)
* **tName**  A character string with name of the tcoord in the ERDDAP dataset \(default “time”\)
* **urlbase**  A character string containing the base URL of the ERDDAP server being accessed \(default “[http://upwell.pfeg.noaa.gov/erddap](http://upwell.pfeg.noaa.gov/erddap)”\)
* **verbose**  A logical variable controling if the verbosity of the URL request should high \(TRUE\) or low \(FALSE\) \(default FALSE\)

**Output**

A dataframe containing:

* column 1 - mean of data within search radius
* column 2 - standard deviation of data within search radius
* column 3 - number of points found within search radius
* column 4 - time of returned value
* column 5 - min longitude of call \(decimal degrees\)
* column 6 - max longitude of call \(decimal degrees\)
* column 7 - min latitude of call \(decimal degrees\)
* column 8 - max latitude of call \(decimal degrees\)
* column 9 - requested time in tag
* column 10 - median of data within search radius
* column 11 - median absolute deviation of data within search radius

**Full reference**

[https://cran.r-project.org/web/packages/rerddapXtracto/rerddapXtracto.pdf](https://cran.r-project.org/web/packages/rerddapXtracto/rerddapXtracto.pdf)

###  plotTrack function

**Summary**  
 plotTrack is a function to plot the results from rxtracto\(\)

**Function**

plotTrack\(resp, xcoord, ycoord, plotColor = “viridis”, name = NA, myFunc = NA, shape = 20, size = 0.5\)

**Arguments**

* **resp**  The data frame returned from rxtracto\(\)
* **xcoord**  The comma separated array \(list\) of numbers containing the x-coordinates of the trajectory that was passed to rxtracto\(\)
* **ycoord**  The comma separated array \(list\) of numbers containing the y-coordinate of the trajectory that was passed to rxtracto\(\)
* **plotColor**  the color palette to use in the plot \(The cmocean color palette by Kristen Thyng [https://matplotlib.org/cmocean/\#colormap-details](https://matplotlib.org/cmocean/#colormap-details)\)
* **name**  A name for color bar label
* **myFunc**  A function of one argument to transform the data
* **shape**  The a numeric code that identifies the symbol to use to mark track \([https://www.datanovia.com/en/blog/ggplot-point-shapes-best-tips/](https://www.datanovia.com/en/blog/ggplot-point-shapes-best-tips/)\)
* **size**  The size of symbol to use to mark track

**Full reference**

[https://rmendels.github.io/rerddapXtracto\_docs/reference/plotTrack.html\#value](https://rmendels.github.io/rerddapXtracto_docs/reference/plotTrack.html#value)

###  rxtracto\_3D function

**Summary**  
Extracts environmental data from an ERDDAP server in an \(x,y,z, time\) bounding box. The same call could be made directly form ERDDAP, but function’s strength is the ability to extract data from polygons.

**Function**  
 extract &lt;- rxtracto\_3D\(dataInfo, parameter = NULL, xcoord = NULL, ycoord = NULL, zcoord = NULL, tcoord = NULL, xName = “longitude”, yName = “latitude”, zName = “altitude”, tName = “time”, urlbase = “[https://upwell.pfeg.noaa.gov/erddap/](https://upwell.pfeg.noaa.gov/erddap/)”, verbose = FALSE\)

**Arguments**

* **dataInfo**  the return from an rerddap “info” call to an ERDDAP server
* **parameter**  character string containing the name of the parameter to extract
* **xcoord**  a real array with the x-coordinates of the trajectory \(if longitude in \#’ decimal degrees East, either 0-360 or -180 to 180\)
* **ycoord**  a real array with the y-coordinate of the trajectory \(if latitude in decimal degrees N; -90 to 90\)
* **zcoord**  a real array with the z-coordinate \(usually altitude or depth\)
* **tcoord**  a character array with the times of the trajectory in “YYYY-MM-DD” - for now restricted to be time.
* **xName**  character string with name of the xcoord in the ERDDAP dataset \(default “longitude”\)
* **yName**  character string with name of the ycoord in the ERDDAP dataset \(default “latitude”\)
* **zName**  character string with name of the zcoord in the ERDDAP dataset \(default “altitude”\)
* **tName**  character string with name of the tcoord in the ERDDAP dataset \(default “time”\)
* **urlbase**  base URL of the ERDDAP server being accessed - default “[http://upwell.pfeg.noaa.gov/erddap](http://upwell.pfeg.noaa.gov/erddap)”
* **verbose**  logical variable \(default FALSE\) if the the URL request should be verbose

**Output**

A dataframe containing: \* extract$data - the data array with dimensions \(lon,lat,time\)

* extract$varname - the name of the parameter extracted
* extract$datasetname - ERDDAP dataset name
* extract$longitude - the longitudes on some scale as request
* extract$latitude - the latitudes always going south to north
* extract$time - the times of the extracts

**Full reference**

[https://rmendels.github.io/rerddapXtracto\_docs/reference/rxtracto\_3D.html](https://rmendels.github.io/rerddapXtracto_docs/reference/rxtracto_3D.html)

###  plotBox function

**Summary**  
 plotBox is a function to plot the results from rxtracto\_3D\(\).

**Function**  
 plotBBox\(resp, plotColor = “viridis”, time = NA, animate = FALSE, name = NA, myFunc = NA, maxpixels = 10000\)

**Arguments**

* **resp**  data frame returned from rxtracto\_3D\(\)
* **plotColor**  the color palette to use in the plot \(The cmocean color palette by Kristen Thyng [https://matplotlib.org/cmocean/\#colormap-details](https://matplotlib.org/cmocean/#colormap-details)\)
* **time**  a function to map multi-time to one, or else identity for animation
* **animate**  animate the plot if there are multiple times \(animate = TRUE to animate\)
* **name**  name for color bar label
* **myFunc**  function of one argument to transform the data
* **maxpixels**  maximum number of pixels to use in making the map - controls resolution

**Full reference** [https://rmendels.github.io/rerddapXtracto\_docs/reference/plotBBox.html](https://rmendels.github.io/rerddapXtracto_docs/reference/plotBBox.html)

###  rxtractogon function

**Summary**  
 The function rxtractogon\(\) extracts a time-series of satellite data that are within a user supplied polygon.

**Function**  
 rxtractogon\(dataInfo, parameter, xcoord = NULL, ycoord = NULL, zcoord = NULL, tcoord = NULL, xName = “longitude”, yName = “latitude”, zName = “altitude”, tName = “time”, urlbase = “[https://upwell.pfeg.noaa.gov/erddap](https://upwell.pfeg.noaa.gov/erddap)”, verbose = FALSE\)

**Arguments**

* **dataInfo**  the return from an rerddap “info” call to an ERDDAP server
* **parameter**  character string containing the name of the parameter to extract
* **xcoord**  a real giving longitudes \(in decimal degrees East, either 0-360 or -180 to 180\) of a polygon
* **ycoord**  a real giving latitudes \(in decimal degrees N; -90 to 90\) of a polygon
* **zcoord**  a real number with the z-coordinate \(usually altitude or depth\)
* **tcoord**  a character array of minimum and maximum times as ‘YYYY-MM-DD’
* **xName**  character string with name of the xcoord in the ERDDAP dataset \(default “longitude”\)
* **yName**  character string with name of the ycoord in the ERDDAP dataset \(default “latitude”\)
* **zName**  character string with name of the zcoord in the ERDDAP dataset \(default “altitude”\)
* **tName**  character string with name of the tcoord in the ERDDAP dataset \(default “time”\)
* **urlbase**  base URL of the ERDDAP server being accessed - default “[http://upwell.pfeg.noaa.gov/erddap](http://upwell.pfeg.noaa.gov/erddap)”
* **verbose**  logical variable \(default FALSE\) if the the URL request should be verbose

**Output**

A dataframe with the structure:

* extract$data - the masked data array with dimensions \(lon,lat,time\)
* extract$varname - the name of the parameter extracted
* extract$datasetname - ERDDAP dataset name
* extract$longitude - the longitudes on some scale as request
* extract$latitude - the latitudes always going south to north
* extract$time - the times of the extracts

**Full reference**

[https://rmendels.github.io/rerddapXtracto\_docs/reference/rxtractogon.html](https://rmendels.github.io/rerddapXtracto_docs/reference/rxtractogon.html)

