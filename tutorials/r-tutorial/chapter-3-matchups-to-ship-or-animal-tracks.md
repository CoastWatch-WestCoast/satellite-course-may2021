# Chapter 3 Matchups to ship or animal tracks

> notebook filename \| 03-xyt\_matchup.Rmd

This exercise you will extract satellite data around a set of points defined by longitude, latitude, and time coordinates like that produced by an animal telemetry tag, and ship track, or a glider tract.

The exercise demonstrates the following techniques:

* Using the **rxtracto** function to extract satellite data along a track 
* Using **rerddap** to retrieve information about a dataset from ERDDAP 
* Using **plotTrack** to plot the satellite data onto a map as well as to make an animation
* Loading data from a tab separated file 
* Plotting the satellite data onto a map

This data is taken from the ERDDAP server at [http://coastwatch.pfeg.noaa.gov/erddap/](http://coastwatch.pfeg.noaa.gov/erddap/)

##  Install required packages and load libraries

```text
# Function to check if pkgs are installed, and install any missing pkgs

pkgTest <- function(x)
{
  if (!require(x,character.only = TRUE))
  {
    install.packages(x,dep=TRUE)
    if(!require(x,character.only = TRUE)) stop(x, " :Package not found")
  }
}

# create list of required packages
list.of.packages <- c("ncdf4", "rerddap","plotdap","rerddapXtracto","parsedate",
                      "graphics", "maps", "mapdata","RColorBrewer","ggplot2", "gifski",
                      "png")

# create list of installed packages
pkges = installed.packages()[,"Package"]

# Install and load all required pkgs
for (pk in list.of.packages) {
  pkgTest(pk)
}
```

##  Get XYZ coordinates

In this exercise we willuse in the XYZ coordinates that have been brought in from a file. Installation of the “rerddapXtracto” package comes with the “Marlintag38606” dataset which we will use for this exercise. It is the track of a tagged marlin in the Pacific Ocean \(courtesy of Dr. Mike Musyl of the Pelagic Research Group LLC\).

The “Marlintag38606” file has this structure:

```text
str(Marlintag38606)
```

```text
## 'data.frame':    152 obs. of  7 variables:
##  $ date  : Date, format: "2003-04-23" "2003-04-24" ...
##  $ lon   : num  204 204 204 204 204 ...
##  $ lat   : num  19.7 19.8 20.4 20.3 20.3 ...
##  $ lowLon: num  204 204 204 204 204 ...
##  $ higLon: num  204 204 204 204 204 ...
##  $ lowLat: num  19.7 18.8 18.8 18.9 18.9 ...
##  $ higLat: num  19.7 20.9 21.9 21.7 21.7 ...
```

We will use the “date”, “lon” and “lat” variables to get the matching satellite data. Here the time variable is already in a date format. Often when reading in your own data you will have to convert the date into a date format \(Remember R syntax is Y for a 4 digit year and y for a 2 digit year\)

```text
## For convenience make shorter names for the variables  
xcoord <- Marlintag38606$lon  
ycoord <- Marlintag38606$lat
tcoord <- Marlintag38606$date
```

## Select the dataset and download its metadata

For this example we will use the SeaWiFS 8-day composite chlorophyll dataset \(ID erdSW2018chla8day\)

**The script below:**

* Gathers information about the dataset \(metadata\) using **rerddap**
* Displays the information

**Set the following arguments for rerddap**

* Set the dataset ID: dataset &lt;- ‘erdSW2018chla8day’
* The default source ERDDAP for **rerddap** is “[https://upwell.pfeg.noaa.gov/erddap](https://upwell.pfeg.noaa.gov/erddap)”. Since we are pulling the data from the ERDDAP at “[http://coastwatch.pfeg.noaa.gov/erddap/](http://coastwatch.pfeg.noaa.gov/erddap/)”, change the url to url = “[http://coastwatch.pfeg.noaa.gov/erddap/](http://coastwatch.pfeg.noaa.gov/erddap/)”

```text
dataset <- 'erdSW2018chla8day'
# Use rerddap to get dataset metadata 
# if you encouter an error reading the nc file clear the rerrdap cache: 
rerddap::cache_delete_all(force = TRUE)
dataInfo <- rerddap::info(dataset, url= "https://coastwatch.pfeg.noaa.gov/erddap/")
# Display the metadata
dataInfo
```

```text
## <ERDDAP info> erdSW2018chla8day 
##  Base URL: https://coastwatch.pfeg.noaa.gov/erddap/ 
##  Dimensions (range):  
##      time: (1997-09-02T00:00:00Z, 2010-12-15T00:00:00Z) 
##      latitude: (-89.95834, 89.95834) 
##      longitude: (-179.9583, 179.9584) 
##  Variables:  
##      chlorophyll: 
##          Units: mg m^-3
```

## Extract the satellite data

* Double check dataInfo to make sure the dataset covers the time, longitude, and latitude ranges in your XYT data.
* Use the name of the chlorophyll parameter that was displayed above in dataInfo: **parameter &lt;- “chlorophyll”**
* Use the xcoord, ycoord, and tcoord vectors you extracted from the marlin tag file.
* Some datasets have an altitude dimension. If so, then zcood must be included in the rxtracto call. The “erdSW2018chla8day” dataset does not include an altitude dimension.
* Define the search “radius” for the gridded data. The **rxtracto** function allow you to set the size of the box used to collect data around the track points using the xlen and ylen arguments. The values for xlen and ylen are in degrees. For our example we 0.2 degrees for both arguments. Note: You can also submit vectors for xlen and ylen, as long as the arethe same length as xcoord, ycoord, and tcoord
* Run the rxtracto function to extract the data from ERDDAP.

```text
parameter <- 'chlorophyll'

xlen <- 0.2 
ylen <- 0.2

# Some datasets have an altitude dimension. If so, then zcood must be included in the rxtracto call.  
# If the dataInfo shows an altitude dimension, uncomment "zcoord <- 0" and include tcoord=tcoord in the rxtracto call.
# zcoord <- 0.

swchl <- rxtracto(dataInfo, 
                  parameter=parameter, 
                  xcoord=xcoord, ycoord=ycoord, 
                  tcoord=tcoord, xlen=xlen, ylen=ylen)
```

```text
## Registered S3 method overwritten by 'httr':
##   method           from  
##   print.cache_info hoardr
```

After the extraction is complete, “swchl” will contain the following columns.

```text
str(swchl)
```

```text
## List of 13
##  $ mean chlorophyll  : num [1:152] 0.0709 0.0729 0.081 0.0826 0.0656 ...
##  $ stdev chlorophyll : num [1:152] 0.0139 0.00192 0.0055 0.00491 0.0026 ...
##  $ n                 : int [1:152] 4 2 12 5 8 9 4 3 0 7 ...
##  $ satellite date    : chr [1:152] "2003-04-19T00:00:00Z" "2003-04-27T00:00:00Z" "2003-04-27T00:00:00Z" "2003-04-27T00:00:00Z" ...
##  $ requested lon min : num [1:152] -156 -156 -156 -156 -156 ...
##  $ requested lon max : num [1:152] -156 -156 -156 -156 -156 ...
##  $ requested lat min : num [1:152] 19.6 19.7 20.3 20.2 20.2 ...
##  $ requested lat max : num [1:152] 19.8 19.9 20.5 20.4 20.4 ...
##  $ requested z min   : logi [1:152] NA NA NA NA NA NA ...
##  $ requested z max   : logi [1:152] NA NA NA NA NA NA ...
##  $ requested date    : chr [1:152] "2003-04-23" "2003-04-24" "2003-04-30" "2003-05-01" ...
##  $ median chlorophyll: num [1:152] 0.0702 0.0729 0.0828 0.085 0.0658 ...
##  $ mad chlorophyll   : num [1:152] 0.01517 0.00202 0.00564 0.00407 0.00243 ...
##  - attr(*, "row.names")= chr [1:152] "1" "2" "3" "4" ...
##  - attr(*, "class")= chr [1:2] "list" "rxtractoTrack"
```

##  Plotting the results

We will use the “plotTrack” function to plot the results.  
 \* “plotTrack” is a function of the “rerddapXtracto” package designed specifically to plot the results from “rxtracto”.

* The example below will use a color palette specifically designed for chlorophyll.

```text
# Uncomment the png line and the dev.off() line to save the image
# png(file="xyt_matchup.png")

plotTrack(swchl, xcoord, ycoord, tcoord, plotColor = 'chlorophyll')

# Uncomment the png line and the dev.off() line to save the image
#dev.off()
```

![](../../.gitbook/assets/r3.5.png)

##  Animating the track

To make a cumulative animation of the track:

```text
plotTrack(swchl, xcoord, ycoord, tcoord, plotColor = 'chlorophyll',
                    animate = TRUE, cumulative = TRUE)
```

##  Try this on your own

This match up was done using weekly \(8-day\) data. Try rerunning the example using the daily \(erdSW2018chla1day\) or the monthly \(erdSW2018chlamday\) satellite data product and see how the results differ

##  Crossing the Dateline

In July 2019 version 0.4.1 of “reddapXtracto”" was updated allowing “rxtracto”" to work on data that crosses the dateline. In this example we will extract chlorophyll data for a grid of stations along the Aleutian Islands.

**Create an station array**  
 For crossing the dateline the longitudes for that animal/ship track must be in 0-360 format.  
 \* Create a grid of stations from 172E to 170W \(190°\) and 50-54N, spced every 2°. \* Then, set up vectors with these values, and then make arrays of the station longitudes and latitudes

```text
lat <- seq(50,54,2)
lon <- seq(172,190,2)

stax <- matrix(lon,nrow=length(lat),ncol=length(lon),byrow=TRUE)
stay <- matrix(lat,nrow=length(lat),ncol=length(lon),byrow=FALSE)
```

To input values into “rxtracto” the longitudes and latitudes need to be in vector format

```text
xcoord <- as.vector(stax) 
ycoord <- as.vector(stay) 
```

Define the search “radius” in the x any y directions, in units of degrees

```text
xlen <- 0.2 
ylen <- 0.2 
```

Create an array of dates. For this exercise we are going to assume all stations were sampled in the same month, so we are going to make all the values the same, but they don’t have to be.

```text
tcoord <- rep('2019-04-15',length(xcoord))
```

Selects the dataset and parameter for the extraction  
 In this example the dataset chosen is the monthly NOAA VIIRS chlorophyll data

```text
dataset <- 'nesdisVHNSQchlaMonthly'
dataInfo <- rerddap::info(dataset)
parameter <- 'chlor_a'
```

## Look at DataInfo to see if dataset has an altitude dimension.

```text
dataInfo
```

```text
##  nesdisVHNSQchlaMonthly 
##  Base URL: https://upwell.pfeg.noaa.gov/erddap/ 
##  Dimensions (range):  
##      time: (2012-01-02T12:00:00Z, 2020-02-01T12:00:00Z) 
##      altitude: (0.0, 0.0) 
##      latitude: (-89.75626, 89.75625) 
##      longitude: (-179.9812, 179.9813) 
##  Variables:  
##      chlor_a: 
##          Units: mg m^-3
```

Since this dataset has an altitude dimension, we need to supply an altitude parameter in the “rxtracto” call

```text
zcoord <- 0.*xcoord
```

Now we will make the call to match up satellite data with station locations.

```text
chl <- rxtracto(dataInfo, 
                  parameter=parameter, 
                  xcoord=xcoord, ycoord=ycoord, zcoord=zcoord,
                  tcoord=tcoord, xlen=xlen, ylen=ylen)
```

Next we will map out the data. Will do this two different ways, using base graphics and using “ggplot”. “plotTrack”, the routine used in the example above, is part of the “rerddapXtracto” package, and is designed to easily plot the output from “rxtracto”, but currently it can not handle crossing the dateline, so we can’t use it for this example.

## Method 1: Make a map using base graphics

First set up the color palette. This will use a yellow-green palette from the Brewer package

```text
cols <- brewer.pal(n = 9, name = "YlGn")
chlcol <- cols[as.numeric(cut(chl$'mean chlor_a',breaks = 9))]
```

Identify stations which have a satellite values

```text
gooddata <- !is.na(chl$'mean chlor_a')
```

Set-up the layout to have a map and a color bar

```text
oldmar <- par("mar")
layout(t(1:2),widths=c(6,1))
par(mar=c(4,4,1,.5))
```

Create the base map, and then overlay stations with data, and then overlay empty circles around all statons

```text
ww2 <- map('world', wrap=c(0,360), plot=FALSE, fill=TRUE)
map(ww2, xlim = c(140, 240),ylim=c(45,70), fill=TRUE,col="gray80",lforce="e")
map.axes(las=1)

points(xcoord[gooddata],ycoord[gooddata],col=chlcol, pch=19, cex=.9)
points(xcoord,ycoord, pch=1, cex=.9)
```

Add the colorbar

```text
par(mar=c(4,.5,5,3))
chlv <- min(chl$'mean chlor_a'[gooddata])+(0:9)*(max(chl$'mean chlor_a'[gooddata])-min(chl$'mean chlor_a'[gooddata]))/10
image(y=chlv,z=t(1:9), col=cols, axes=FALSE, main="Chl", cex.main=.8)
axis(4,mgp=c(0,.5,0),las=1)
```

##  Method 2: ggplot graphics.

ggplot handles colorbars much easier than base graphics!

Put station lat, long and chl values into a dataframe for passing to ggplot

Get land boundary data in 0-360 units of longitude.

Make the map

```text
ggplot(chlsta) +
  geom_point(aes(x,y,color=chl)) +
  geom_polygon(data = mapWorld, aes(x=long, y = lat, group = group)) + 
  coord_cartesian(xlim = c(140,240),ylim = c(47,70)) +
  scale_color_gradientn(colours=brewer.pal(n = 8, name = "YlGn")) +
  labs(x="", y="")
```

![logo](data:image/png;base64,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)

