# ERDDAP Introduction

[Permalink](https://github.com/CoastWatch-WestCoast/satellite-course-may2021/blob/57de06ed1187915df236dfd7e11e9482840042be/tutorials/erddap/README.md)

## ERDDAP

### What is ERDDAP

For many users, obtaining the ocean satellite data they need requires downloading data from several data providers, each with its own file formats, download protocols, subset abilities, and preview abilities.

> **A short list of ocean satellite data providers**  
>  Jet Propulsion Laboratory PO.DAAC  
>  Ocean Biology \(OB.DAAC\)  
>  Goddard Space Flight Center  
>  Center for Satellite Applications and Research  
>  CoastWatch Central Operations  
>  Office of Satellite and Products  
>  National Centers for Environmental Information  
>  Comprehensive Large Array-data Stewardship System  
>  European Space Agency  
>  Japan Aerospace Exploration Agency

The goal behind ERDDAP is to make it easier for you to get scientific data. To accomplish that goal, ERDDAP acts as a middleman, selectively channeling datasets from remote and local data sources to a single data portal. With ERDDAP as the single-source portal, you have access to a simple, consistent way to download subsets of gridded and tabular scientific datasets in common file formats, with options and make graphs and maps.

![](../../.gitbook/assets/erddap%20%281%29.png)

_Features of ERDDAP_

* Data in the common file format of your choice. ERDDAP offers all data as .html table, ESRI .asc and .csv, Google Earth .kml, OPeNDAP binary, .mat, .nc, ODV .txt, .csv, .tsv, .json, and .xhtml
* ERDDAP can also return a .png or .pdf image with a customized graph or map
* Standardized dates/times \(“seconds since 1970-01-01T00:00:00Z” in UTC\)
* A graphical interface for humans with browsers
* RESTful web services for machine-to-machine data exchange and downloading data directly into your software applications \(e.g.Matlab, R, Python…\) and even into web pages.

