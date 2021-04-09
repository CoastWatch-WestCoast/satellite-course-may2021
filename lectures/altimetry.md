# Altimetry
<center>

![Sea Surface Anomaly](../images/sla_globe.png)

</center>
<p align="center">

<img src="../images/sla_globe.png">

</p>
This lecture is also available as part of an audio-narrated [PowerPoint presentation](https://oceanwatch.pifsc.noaa.gov/files/hawaii2020/05-Salinity-Winds-Altimetry.pptx).

## What is altimetry? <a id="what-is-altimetry"></a>

The surface of the ocean isn’t flat -- there are high spots and low spots.

Satelllite altimeters measure the ocean surface height in relation to the mean sea level. Altimetry data helps identify areas of upwelling and downwelling and the location of ocean current features and eddies.

## Basic principle <a id="basic-principle"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8vETWUDNW8v-cuXEV%2F-Lz9FGq4aboLFaogm02k%2Fimage.png?alt=media&token=c87132b4-c131-48a7-92ad-909a19a63c8e)

https://www.star.nesdis.noaa.gov/socd/lsa/AltBathy/

Satellite altimeters are **active microwave** instruments \(-&gt; not affected by cloud cover\)

Altimeters on board the satellites send signals at high frequencies \(over 1,700 pulses per second\) to Earth’s surface and receive the echoes from the surface.

The return time of the signal gives a measure of distance to the surface \(**range,** R\)

However, as electromagnetic waves travel through the atmosphere \(twice\), they can be decelerated by water vapor or ionization.

 -&gt; need atmospheric correction for accurate measurements

The precise position of the satellite is tracked using Doppler shift, GPS or lasers, to determine the **satellite altitude,** which is the distance to a standard reference \(**ellipsoid**\).

The range is subtracted from the altitude of the satellite to give **Sea Surface Height** \(SSH\).

Altimetry data has an accuracy of ~ 3cm !! But a low resolution \(~ 25 km\), and no coverage close to the coasts \(20km\).

## Sea Surface Height <a id="sea-surface-height"></a>

The sea surface height \(SSH\), is the satellite’s distance at a given instant from the reference surface, so:

 SSH = Altitude – Range.

For the ocean, the sea surface height integrates effects such as:

 - The sea surface height which would exist without any perturbing factors \(wind, currents, tides, etc.\). This surface, known as the geoid, is determined by gravity variations around the world, which are in turn due to major mass and density differences on the seafloor.

 - The ocean circulation, or dynamic topography, which comprises:

* the permanent stationary component \(permanent circulation linked to Earth’s rotation, permanent winds, etc.\). The mean effect is of the order of one meter.
* a highly variable component \(due to wind, eddies, seasonal variations, etc.\).

## Sea Level Anomalies <a id="sea-level-anomalies"></a>

A **sea level anomaly** \(SLA\) is the difference between the total sea-level and the average sea-level for a particular time of year.

We look at anomalies because the total level measurement made by the altimeter varies from +/- 100 meters. Most of this is constant, though, and is due to the Earth's gravity \(geoid\) and the ocean circulation.

Sea level variations caused by El Niño for example account for only 1% of the signals. If the constant part was not removed, the El Niño signal would not be observable.

To derive the dynamic topography, the easiest way would be to subtract the geoid height from SSH. In practice, mean sea surface is subtracted instead, to yield the variable part \(sea level anomalies\) of the ocean signal.

SLA = SSH – MSS

MSS represents the mean profile of the SSH over a defined temporal period, also called reference period \(currently 1993-2012\).

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8vETWUDNW8v-cuXEV%2F-Lz9GhPmiA144sagqftT%2Fimage.png?alt=media&token=4c6f50ff-e671-414d-b349-094b99554539)

https://duacs.cls.fr/faq/what-are-the-product-specification/altimeter-reference-period-and-absolute-reference/

## Geostrophic currents <a id="geostrophic-currents"></a>

At large space scales in the ocean, pressure gradients due to gradients in sea level are balanced by the Coriolis force and associated geostrophic currents.

SLA obtained from satellite altimetry measurements is used to derive surface geostrophic currents.

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz9GlyeuT-QJ8yZ79Kv%2F-Lz9H4udKtmGGtUAETfT%2Fimage.png?alt=media&token=00391bee-45f8-4a29-bab1-3d12e538073b)

http://www.seos-project.eu/modules/oceancurrents/oceancurrents-c06-s02-p01.html

## Geostrophic currents & SLA <a id="geostrophic-currents-and-sla"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz9GlyeuT-QJ8yZ79Kv%2F-Lz9HG8jAgBIvEbl6Nk3%2Fimage.png?alt=media&token=c0370973-aca9-4616-a99d-b2bce626957d)

Son et al, 2014

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz9GlyeuT-QJ8yZ79Kv%2F-Lz9HOGPIraPgEBirTKX%2Fimage.png?alt=media&token=04229fcc-5106-4b6d-9268-3aac862a908b)

Average geostrophic currents – 1992 -2002, Cheng et al, 2014

## Eddies <a id="eddies"></a>

Eddies can be identified from SLA.

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz9GlyeuT-QJ8yZ79Kv%2F-Lz9HbqUJ8ab8Gax7CRa%2Fimage.png?alt=media&token=c423b5c2-ac47-44f8-9ab0-073c4ada576a)

Cheng et al, 2014

The spatial and temporal resolutions of SLA are 25 km and 7 days, respectively, thus an eddy diameter smaller than 50 km or a lifespan shorter than one week can not be detected using altimetry data.

## Altimetry missions <a id="altimetry-missions"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz9GlyeuT-QJ8yZ79Kv%2F-Lz9HlFwrDlqGro8Iq3f%2Fimage.png?alt=media&token=5f382b00-342a-4674-8bc2-32d9d3617251)

CLS/CNES

## Current missions <a id="current-missions"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz9GlyeuT-QJ8yZ79Kv%2F-Lz9Ht9JsotY3soNFC9s%2Fimage.png?alt=media&token=80cf661c-f204-4051-9153-6ae48efd16fe)

From: Eric Leuliette, NOAA/NESDIS

## Current constellation coverage <a id="current-constellation-coverage"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz9GlyeuT-QJ8yZ79Kv%2F-Lz9I3ma9E9gfgFnsUJw%2Fimage.png?alt=media&token=caf1bd00-6f96-47b7-adf0-491658403839)

Jason-2, Jason-3, Sentinel-3A, AltiKa, Cryosat-2. From: Eric Leuliette, NOAA/NESDIS

Much of the ocean surface is interpolated: low spatial resolution ~ 25km, 7 days

## Data products <a id="data-products"></a>

* AVISO data. Distributed by CMEMS \(Europe\). Free for research purposes but need to register to get access. [http://marine.copernicus.eu/services-portfolio/access-to-products](http://marine.copernicus.eu/services-portfolio/access-to-products/)​[/](http://marine.copernicus.eu/services-portfolio/access-to-products/)
* 
![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz9GlyeuT-QJ8yZ79Kv%2F-Lz9IjQal50T5MWp3l0E%2Fimage.png?alt=media&token=dfa18b69-5a75-45fe-b5c6-45711b879cb3)

From: Eric Leuliette, NOAA/NESDIS

​

## References <a id="references"></a>

* * * * * * Son et al 2014. A newly observed physical cause of the onset of the subsurface spring phytoplankton bloom in the southwestern East Sea/Sea of Japan. Biogeosciences 11\(5\)
* Cheng et al, 2014. Statistical Characteristics of Mesoscale Eddies in the North Pacific Derived from Satellite Altimetry. Remote Sensing 6\(6\)

​ ​

​ ​

