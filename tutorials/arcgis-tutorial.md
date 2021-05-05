# ArcGIS tutorial

​

This tutorial will teach you how to import NetCDF data into ArcGIS, extract environmental values at survey locations, or within polygons. Finally, you'll learn how to create a habitat map based on a range of SST values.

You will need the **spatial analyst** extension to complete this tutorial.

## Introduction <a id="introduction"></a>

Esri’s ArcMap is a program with an intuitive graphic user interface. Once you are familiar with the general structure of the program, it is easy to navigate. The trade-off is that it can be very slow. Please be aware that you might need patience if working with large datasets.

In Esri’s world, data with x \(long\), y \(lat\) and time dimensions, like ocean satellite data, are called **multi-dimensional data**. ArcMap wasn't originally designed to work with multi-dimensional data. Depending on how the data is configured, some functions may or may not be available and processing of the data may take a long time. \(R is a great alternative for large datasets!\)

Before starting the tutorial:

* Open an empty ArcMap, in the Catalog window, click on the “Connect to Folder” button, and make the connection to your working folder
* In ArcMap, click on “Customize” in the top menu, and “Extensions...”, and make sure the “Spatial Analyst” extension is checked.

## 1. General Navigation of ArcMap <a id="1-general-navigation-of-arcmap"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-lxyXVTGlItYRByips%2F-M-lyM2wOFfYFm4DzTv3%2Fimage.png?alt=media&token=4cdd1815-bc4e-4b8c-9a54-bd28e9ed6cb3)

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-lxyXVTGlItYRByips%2F-M-lyZ6gGU98RxNtIPvq%2Fimage.png?alt=media&token=2fc21641-963d-4b79-b89d-8013e7d25158)

Mousing over individual icons displays descriptions of each tool. Greyed-out tools are not available to use.

## 2. Download NetCDF data from ERDDAP <a id="2-download-netcdf-data-from-erddap"></a>

Let's download some monthly SST data to work with.

Go to: [https://oceanwatch.pifsc.noaa.gov/erddap/griddap/CRW\_sst\_v1\_0\_monthly.html](https://oceanwatch.pifsc.noaa.gov/erddap/griddap/CRW_sst_v1_0_monthly.html)​

Make sure to select a reasonable subset in time and space \(see example below\). The amount of data that can be directly downloaded from ERDDAP is limited. Downloading a reasonable amount of data will also help the processing time in ArcGIS. Because of the download and processing limits, it is not recommended to work with a long time-series in ArcGIS \(for example, 365 days of daily chl-a, or 20 years of monthly composite of sst\).

Change the File type to “.nc – Download a NetCDF-3 binary file with COARD/CF/ACDD metadata”.

Once the settings are entered, click on the Submit button to download.

Save the downloaded file on your computer.

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-mCYx20HIAx-_-vD0A%2F-M-mDeaIh99X4c3Wop2I%2Fimage.png?alt=media&token=cafe8914-ed9a-4344-b5b5-1f81b635b47b)

## 3. Import data into ArcGIS Desktop <a id="3-import-data-into-arcgis-desktop"></a>

* In the ArcMap’s Search Window \(top right side of the screen\), type in “Make NetCDF Raster Layer”.
* Click on “Make NetCDF Raster Layer \(Multidimension\)” in the list to open the tool dialog box.
* Browse to the downloaded NetCDF file, and click “Open” to select the file as Input netCDF File. Notice that Variable, X Dimension, Y Dimension are automatically filled out.
* Keep Output Raster Layer as analysed\_sst\_Layer.
* Click OK

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-mCYx20HIAx-_-vD0A%2F-M-mDvecqXX3zW4MqqgT%2Fimage.png?alt=media&token=0b591464-9fe7-4baf-898b-d9bf8ddf3644)

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-mCYx20HIAx-_-vD0A%2F-M-mE4xAjzR-as0PidF-%2Fimage.png?alt=media&token=1bf0ad4e-319a-40f8-87a8-25793f299dd9)

## 4. Enable the Time Slider <a id="4-enable-the-time-slider"></a>

* In the table of contents, right click analysed\_sst\_Layer, and then click on “Properties”.
* Under the Time tab of the Properties window, check “Enable time on this layer”.
* Change the Time dimension to time.
* Change the Time Step Interval to an appropriate interval. Since this example is a monthly composite, change it to 1.00 Months.
* Click OK

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-m7VG-Cc3-lqpnw7gW%2F-M-m7la8OX3AgnoEWafv%2Fimage.png?alt=media&token=b998862d-5188-41ea-ae97-8f1003da4998)

* In the Tools toolbar, click on the Time Slider button:

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-m7VG-Cc3-lqpnw7gW%2F-M-m881NGD9bJoFxk9pc%2Fimage.png?alt=media&token=1a91318a-58e3-4041-aae9-3094f7910364)

* In the Time Slider window, click the play button to see the changes of SST over time:

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-m7VG-Cc3-lqpnw7gW%2F-M-m8TY5oBsqDePaTzXc%2Fimage.png?alt=media&token=ab429bbc-f281-4e35-9e32-a981c7473781)

If it plays too fast or too slow, click on the Options button, and under the Playback tab of the Time Slider Options, adjust the playing speed. You can also export the animation as a movie file \(using the “export to video” button\), however the quality of the movie is dependent on the size of the data and the graphics card of the computer.

## 5. Create a map <a id="5-create-a-map"></a>

You will need to download the [esd\_fish\_survey\_2016.csv](http://oceanwatch.pifsc.noaa.gov/files/esd_fish_survey_2016.csv) file and save to your working folder.

* If the analysed\_sst\_Layer is still playing, click the Pause button. You can adjust the time to a month of particular interest for which you want to create a map
* In the Catalog window, navigate to your working folder on your desktop.
* Drag and drop the “esd\_fish\_survey\_2016.csv” file into the map
* Right-click the added table in the table of contents, and click “Display XY Data”...
* In the “Display XY Data” window, choose LONGITUDE as X Field, and LATITUDE as Y Field.
*  Click on the “Edit...” button to choose WGS 1984 coordinate system by expanding Geographic Coordinate Systems Folder&gt; World&gt; WGS 1984 and click OK

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-mB42lyM8KmYj_Htqs%2F-M-mBJlUJssTxAl0O5Rw%2Fimage.png?alt=media&token=ed80671c-807a-4def-9ce0-7e3f7bc315e5)

* Click OK to the message “Table Does Not Have Object-ID Field”
* The layer added is a temporary layer from the table. To make it permanent, you will have to export it as a shapefile by right-clicking the esd\_fish\_survey\_2016.csv Events layer and then Data &gt; Export Data...
* Browse to the ArcGIS\_PIFSC\_demo folder, select type “shapefile” and save it as esd\_fish\_survey\_2016\_export.shp
* Right-click the exported shapefile, and click “Zoom to Layer”

**If you already know how to create a map in ArcMap, you can skip this part of the tutorial.**

* On the top menu, click View &gt; Layout View Layout view will allow you to create a map with your data, and insert map elements like a North Arrow, a Legend, and a Scale Bar
* On the top menu, click Insert &gt; Legend
* In the Legend Wizard window, click through Next to accept all the default settings and click Finish to generate the Legend
* To change the descriptions on the legend, you will have to change them in the table of contents.
* Right click the exported shapefile, click on Properties, change the name to 2016 Fish Survey Sites under the “General” tab, and click OK.
* Follow the same steps for anlysed\_sst\_Layer, and change the name to SST
* Right-click the legend on the map, and click on Properties. Under the “General” tab, delete Legend, under the “Frame” tab, change the background to white, and click OK
* From the top menu, insert a North Arrow of your choice, and a scale bar.
* To change the unit of the scale bar, right click the scale bar, and click on Properties. Under the Scale and Units bar, change the division units to Kilometers

The map should look like this:

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-mCYx20HIAx-_-vD0A%2F-M-mFqnxc-_aP6Liy6Pd%2Fimage.png?alt=media&token=9dfb18c0-4129-4123-bbfe-ec49035f4304)

* You can export the map as a PDF by clicking "File" in the top menu and "Export Map".
* Choose PDF for “Save as type” and save the map on your computer.
* To save the map you created, click on the Save button \(floppy disk button\) and save the project as “sst\_netcdf\_map.mxd” on your computer.

Since the longitude range in the NetCDF file is from 0 to 360 degree, the SST data may not align with the fish survey data. There are a couple of ways to fix this issue... The easiest way is to change the projection of the map document to your data, instead of changing the NetCDF data. In the Table of Contents, click on Layers \(on the very top\), and click on Properties. Under the Coordinate System tab, expand Layers folder, and GCS\_WGS\_1984. Select your data under GCS\_WGS\_1984, and click OK.

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-mCYx20HIAx-_-vD0A%2F-M-mGKZOFUoot77kS6ps%2Fimage.png?alt=media&token=62688d1a-d979-4023-a46a-03a879aba6cb)

* If you are in the layout view, go back to the data view by clicking View on the top menu, and click on Data View
* In the table of contents, right click on the SST layer, and click on Properties
* Under the NetCDF tab, choose time for Band Dimension and click OK
* In the Search window, search for the "Sample" tool
* Click Sample \(Spatial Analyst\) tool and fill in the following parameters
  * Input rasters: SST layer
  * Input location raster or point features: 2016 Fish Survey Sites shapefile
  * Output table: sample\_sst\_w\_fishsites\_new.dbf
  * Resampling technique: NEAREST
  * Unique ID field: SITEVISITID
* Click OK to run the tool, and once it is completed, click Close
* Right click sample\_sst\_w\_fishsites\_new in the table of contents, and Open the table
* Notice the column names don’t indicate the months, but it starts from the first month in the SST dataset to the last month.

## 7. Export the SST layer <a id="7-export-the-sst-layer"></a>

The SST Layer is a temporary file, displayed from the NetCDF file. To make it permanent and make it easier to work with in ArcMap, the layer needs to be exported.

* If you have not done so, in the table of contents, right click on the SST layer, and click on Properties. Under the NetCDF tab, choose time for Band Dimension and click OK to make sure that the different time steps will be exported properly. \(Note: When this is done, the time slider won’t work properly anymore ….\)
* Right-click on the SST layer, then click on Data and Export Data
* Set the Location to your working folder.
* Name it SST\_Layer1.tif, set the format to TIFF and click on “Save”.
* Click Yes to add the exported data as a layer.

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-qCyHKaHxqnByE68bh%2F-M-qDHRMQbMtr7claVMz%2Fimage.png?alt=media&token=8c6da29a-d563-45aa-8ce6-5b7dd3c1012c)

If the new layer looks weird, with just red, blue, and green colors instead of a color scale, right-click on the layer, Properties, Symbology, then click on “Stretched” instead of “RGB Composite” in the list on the left and select an appropriate color scale \(You might need to click on “Invert” to make sure warm colors correspond to high values\).

## 8. Calculate statistics within polygons <a id="8-calculate-statistics-within-polygons"></a>

Let’s calculate some summary statistics of SST within a shapefile. First, you will need to download the [Satellite toolbox](https://oceanwatch.pifsc.noaa.gov/files/Satellite.tbx) and the [3 nautical mile boundary shapefile](http://oceanwatch.pifsc.noaa.gov/files/3_naut_mile_bndry.zip). Save the files to your working directory, and unzip the shapefile.

The “Zonal statistics as table” tool from the Spatial Analyst extension allows users to calculate summary statistics from raster data over a specific zone \(a polygon or another raster\). However, it can only be run on one raster layer \(or raster band, i.e. time step in our case\) at a time. Some analyses may require running the tool multiple times. For this training, a custom model was built to run the tool on multiple raster bands \(i.e. time steps\) in one go.

* In the Catalog window, navigate to your working folder, and drag the 3\_naut\_mile\_bndry\_wgs84.shp to the table of contents. Using this shapefile, we will compute statistics of SST within the 3 nautical mile boundary, for each island.
* To make sure the layers display properly, you can manually change the order of the layers. Click the top left icon in the Table of Contents: “List by drawing order”. Then click-and-drag the 3\_naut\_mile\_bndry\_wgs84.shp layer above the chl-a layer in the Table of contents.

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-qE2TkrdWE1WVsvGQc%2F-M-qGb4agiG1oOY48RJR%2Fimage.png?alt=media&token=c08e6c4e-364a-4a37-a488-d5f86ede3858)

* Right-click on the 3\_naut\_mile\_bndry\_wgs84.shp shapefile in the table of contents, and Open Attribute Table
* Notice that there are 8 records, with each record corresponding to a polygon, for each island.
* In the Catalog window, navigate to your working folder, and locate the toolbox Satellite.tbx

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-qE2TkrdWE1WVsvGQc%2F-M-qHtGq8f5nWlCGWoN1%2Fimage.png?alt=media&token=971fd16a-b079-4831-94b5-50841957950e)

* Expand the Satellite.tbx.
* Double-click the “ZonalSt\_Merge” tool.
* Enter the parameters as follows:
  * Input Raster: SST\_Layer1.tif **Note: make sure to browse to your working folder so that the path to the layer is entered**
  * Number of Bands: Up to 12 \(needs to match the number of bands, aka time steps, from the NetCDF file\)
  * Zone Polygon: 3\_naut\_mile\_bndry\_wgs84.shp
  * Zone Polygon Id: Island\_Name
  * Output Workspace: your working folder
* Click OK to run the tool
* In working folder, find ZonalStatistics\_Output.dbf, drag and drop into ArcMap. If you can not find the file in your catalog window, you might have to disconnect the folder \(right-click, “disconnect folder”\) and reconnect to it, or you can open the file in Excel instead.
* Right-click the dbf file in the table of contents, and click Open
* Note that the table is organized by island name and by Band \(i.e. month \# in our case\)

## 9. Suitability model – TurtleWatch <a id="9-suitability-model-turtlewatch"></a>

TurtleWatch is a tool developed by Dr. Evan Howell \(NOAA/PIFSC, Howell et al, 2008, 2015\) to advise longline fishermen on areas to avoid to reduce their likelihood to interact with loggerhead turtles which are a protected species.

Every year, the Hawaii-based shallow-set longline fishery has a cap of interactions which triggers a fishery closure when it’s exceeded. For 2019, the cap was 17 interactions for loggerhead turtles.

For loggerhead turtles, Howell et al 2008 showed that 50% of interactions have historically happened in waters with 17.5ºC &lt; SST &lt; 18.5ºC.

Let’s create a map of the zone to avoid for a given day.

* * Start a new map in ArcMap.
* Use the “Make NetCDF Raster Layer” to import the data into ArcMap. You’ll notice that the range of values is between 283 and 300. These are degrees Kelvin. We are going to need to convert these values to degrees Celsius.
* In the search box, type “Raster Calculator” and open the tool.
* Drag your layer name in the middle box and type “- 273.15”. Click ok

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-qLM9rtKzMtH3O_vwk%2F-M-qMdJ1HOjpVV-kLTWT%2Fimage.png?alt=media&token=2b6ee058-b6a4-4ef8-af05-50fbc12d49c0)

* In the search box, type “Reclassify” and open the “Reclassify \(Spatial Analyst\)” tool.
* Select your new SST layer \(in ºC\) as the input layer and click on the “Classify…” button.
* Change the number of classes to 3 and edit the 1st and 2d break values to 17.5 and 18.5 respectively and click OK.

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-qMzF69waq2C3CuS54%2F-M-qNH7SmvNfseteOnzU%2Fimage.png?alt=media&token=06671467-3db2-4e13-bb7f-236c3e3bd052)

* On the first screen, change the new values to 0, 1, 0, then click ok.

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-qNND03xEl-5TfTyzF%2F-M-qNfmP323rWWenDU9C%2Fimage.png?alt=media&token=ecfc9ab8-685a-40d4-a188-85549bf77de6)

* Change the color for each class \(by right-clicking on each symbol\) to “No color” and dark red respectively.
* Remove the layer in Kelvin, and change the color scale for the SST layer \(right-click, Properties, Symbology\).

You now have a map of the zone to avoid. Add a graticule \(in Layout View, click on View, Data Frame Properties, Grids\), a legend and send it to your favorite longline fisherman!

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-qNND03xEl-5TfTyzF%2F-M-qNvT0S1Bjv-8bsfFZ%2Fimage.png?alt=media&token=bc52ff59-b5e8-4452-a097-9e8c2d54c2b2)

For more information on suitability modeling \(and on how to build more complex habitat models in ArcMap\), this free ESRI tutorial might also be of interest \(click on “Lessons and resources” to go straight to the tutorial about bob cat habitat suitability\):

​

​

​

