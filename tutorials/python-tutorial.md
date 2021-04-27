---
description: Exercises using Python to download and process satellite ocean data.
---

# Python tutorials

### Viewing the exercises

The exercises are a series of Jupyter Notebooks that are hosted on a GitHub repository. You can view a single exercise to see if it is of interest by clicking below on the linked name of each exercise. A non-executable version of the exercise will open in a new browser window. 

If you want an executable version of a Notebook,  go to the GitHub repository and download a zip file with all of the exercises included:

* Go to: [https://github.com/CoastWatch-WestCoast/python\_code](https://github.com/CoastWatch-WestCoast/python_code)
* On the green "Code" dropdown, select "Download Zip"
* Unzip to a location on your computer
* In a terminal, navigate to the unzipped folder and launch Jupyter Notebook by entering:

  ```text
  jupyter notebook
  ```

### Software Requirement

[Python 3](https://www.python.org/) is required to participate in the Python tutorials and examples presented in the course.   

[Anaconda](https://docs.anaconda.com/anaconda/install/) installations have made it easier to install the required modules. [Miniconda](https://docs.anaconda.com/anaconda/install/) is a light weight version of Anaconda that takes up less disk space. It comes with a minimal set of modules, so you add just what you need. The following modules are required: pyproj, netCDF4, requests, matplotlib, pandas, cartopy, xarray, statsmodels, shapely, and cmocean. You can run this [script](https://github.com/CoastWatch-WestCoast/python_code/blob/main/check_modules.py) in your python environment to check if the modules are install. 

[Jupyter Notebooks ](https://jupyter.org/install)in addition to Python 3 will be used for Python exercises. 

### Exercises

1. \*\*\*\*[**Emulating the R rerddapXtracto functions**](https://github.com/CoastWatch-WestCoast/python_code/blob/main/virtual_buoy_example_geopolar.ipynb) This exercise shows you how to duplicate the rerddapXtracto functions demonstrated in R tutorial section of the course.
   * Extract environmental data from an ERDDAP server along an x,y and time trajectory, e.g. an animal or cruise track.
   * Extract environmental data from an ERDDAP server in an rectangular bounding box \(polygon\) over time.
   * Extract environmental data from an ERDDAP server in an irregular bounding box \(polygon\) over time, e.g. a marine protected area.
2. \*\*\*\*[**Creating a virtual buoy data**](https://github.com/CoastWatch-WestCoast/python_code/blob/main/virtual_buoy_example_geopolar.ipynb)  Create a virtual buoy from satellite data for locations where in-situ buoy data may not be available or has been discontinued.
3. \*\*\*\*[**Comparing time series from different sensors**](https://github.com/CoastWatch-WestCoast/python_code/blob/main/compare_sensor_data.ipynb) Several ocean color sensors have been launched since 1997 to provide continuous global ocean color data. Chlorophyll-a values can vary among the sensors during periods where measurements overlap. This exercise examines that variability.

​

