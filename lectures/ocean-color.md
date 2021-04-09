# Ocean Color

![VIIRS SNNP Sensor September 2020](../.gitbook/assets/chl_globe.png)

This lecture is also available as an audio-narrated [PowerPoint presentation](https://oceanwatch.pifsc.noaa.gov/files/hawaii2020/03-Ocean_Color.pptx).

## Objectives <a id="objectives"></a>

Establish baseline vocabulary/concepts:

* How is ocean color measured from space
* Spectral characteristics of oceanic waters
* Sensor bands
* True color images
* Sun glint
* Ocean color data products
* Case-1 vs case-2 waters
* Sensors
* ESA-CCI product
* Multi-spectral vs. Hyper-spectral sensors

## Why ocean color? <a id="why-ocean-color"></a>

It is feasible to measure phytoplankton pigments, and productivity on a global scale.

This feasibility rests squarely on two observations:

1. There exists a more or less universal relationship between the color of the ocean and the phytoplankton pigment concentration for most open ocean waters
2. It is possible to develop algorithms to remove the interfering effects of the atmosphere from the imagery.

Ocean color measurements from space have revolutionized our understanding of the ocean on every scale, from local to global and from days to decades.

Ocean color measurements reveal a wealth of ecologically important characteristics including:

* chlorophyll concentration \(a proxy for the biomass of marine plants or phytoplankton\)
* the rate of phytoplankton photosynthesis
* sediment transport
* dispersion of pollutants
* responses of oceanic biota to long-term climate changes

## What causes variation in the color of the ocean? <a id="what-causes-variation-in-the-color-of-the-ocean"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8mDeTesE-PN2-5RSD%2Fimage.png?alt=media&token=db534519-896d-4af6-8c96-43ef1a4d04af)

## Reminder: What is measured by the sensors? <a id="reminder-what-is-measured-by-the-sensors"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8mKo1jyeOmosv4LUq%2Fimage.png?alt=media&token=6f844030-0b92-4165-9200-3dd8f15eb9c4)

Ocean color measurements focus on light emitted in the visible range

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8mT56qoJrSq1lUNpS%2Fimage.png?alt=media&token=b6f5aad6-7f57-478f-b985-3b0938a8674d)

From: Jeremy Werdell, NASA

## Light Penetration <a id="light-penetration"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8mfUOf_-WQkHYs7PF%2Fimage.png?alt=media&token=6a1477ff-5a1b-4d91-ba81-64d9c1dabe00)

Transmission of light in “pure” fresh or saltwater

* Blue light is scattered by clear water
* Red light is absorbed

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8moRJn9cdIUvJ1Q2F%2Fimage.png?alt=media&token=3b97cc59-f95f-4057-976f-9caae6570070)

Algae and tannins absorb blue and green -&gt; the water looks more brownish

## Definitions <a id="definitions"></a>

* **Downwelling irradiance**: Ed Flux of light passing down through the sea surface into the water column
* **Water-leaving radiance**: Lw A measure of how much light is leaving the sea surface and subsequently propagates to the top of the atmosphere
* **Remote sensing reflectance**: RRS A measure of the proportion of the downwelling light that is reflected back up from the water below. It contains the spectral color information of the water body \(below the sea surface\). Rrs is the ratio between the water-leaving radiance \(Lw\) and the downwelling irradiance \(Ed\).

RRS=Lw/EdRRS = Lw/EdRRS=Lw/Ed

* **Absorption**: a Absorption of light takes place when matter captures electromagnetic radiation, converting the energy of photons to heat.
* **Scattering**: b Light scattering changes the direction of photon transport, “dispersing” them as they penetrate a sample, without changing their wavelength.
* Both absorption and scattering reduce the light energy in a beam as it travels through water. While scattering redirects the angle of the photon path, absorption removes the photons permanently from the path.
* Reflectance is related to absorption and scattering:

 RRS ~ coeff \* b/a

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8nbBTNJ9Zo2Q0Iy7V%2Fimage.png?alt=media&token=196e6e0d-7b4b-4c84-bfc7-a1e57113d7a7)

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8ngH5yGSMo3mzWpgL%2Fimage.png?alt=media&token=7d92c38d-f99e-4deb-a65b-3fc5e0e9f972)

Reflectance is affected by the concentration of pigments in the water

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8nmlG4vFoLbP9tGX-%2Fimage.png?alt=media&token=ad78f202-b5bf-4377-a722-8660645cb1d8)

## Reminder: Electromagnetic radiation \(EMR\) <a id="reminder-electromagnetic-radiation-emr"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8nstyCgAm4KlfMoV3%2Fimage.png?alt=media&token=78bda160-a2a3-4ee3-8b8e-282b6fbbbaba)

Credit: Jan Yoshioka, CI

## Steps for deriving ocean color data products from space <a id="steps-for-deriving-ocean-color-data-products-from-space"></a>

Deriving biological parameters from ocean color measurements is a multi-stage process.

* Ocean color radiometric sensors measure the upwelling radiance at the top of the atmosphere \(LTOA\). LTOA is the total radiance from three sources:
  * **water-leaving \(Lw\) radiance**
  * radiance reflected from the sea surface \(**surface-reflected radiance**\)
  * radiance scattered into the viewing direction by the atmosphere along the path between the sensor and sea surface \(**atmospheric path radiance**\).
* Of these three radiance sources, **the desired measurement is Lw**. Lw carries information about the biological and chemical constituents in the near-surface waters.
* To obtain Lw, it is necessary to deduce and remove the contributions of surface reflection and atmospheric path radiance from the measured total, a process known as **atmospheric correction**. This is difficult because Lw is no more than 10 percent of LTOA.

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8oiztjMdHAZFNV5Z8%2Fimage.png?alt=media&token=61ce1c4c-9efb-4bb4-95d4-6d32c4fa0e9e)

From: Jeremy Werdell, NASA

## Atmospheric correction <a id="atmospheric-correction"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8osvrvrBKWRaCoOhD%2Fimage.png?alt=media&token=f7e882fb-47f7-40b5-b24a-9eb96ede9e23)

From: Jeremy Werdell, NASA

The water signal is often less than 10% of the total signal measured by the sensor

-&gt; good atmospheric correction is critical

## “Ocean color” enables studying microscopic marine features from space <a id="ocean-color-enables-studying-microscopic-marine-features-from-space"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8p2_tzlKoWwNWoUnq%2Fimage.png?alt=media&token=9d28dbc1-028e-4668-a248-55e3938b333c)

From: Jeremy Werdell, NASA

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8pADPodJpxlm5ORV-%2Fimage.png?alt=media&token=509a8649-5fe9-4938-a23a-3b6f9ddf7889)

From: Jeremy Werdell, NASA

The color of the ocean is a function of light that is absorbed or scattered as a result of constituents in the water.

* Phytoplankton and pigments
* Dissolved organic matter
* Detritus \(fecal pellets, dead cells\)
* Inorganic particles \(sediment\)
* Water absorption

## Reminder: Sensor bands <a id="reminder-sensor-bands"></a>

Multispectral radiometers measure EMR intensity at a few discrete wavelength regions. Each wavelength region is defined by a central wavelength and a small range of wavelengths around it \(a bandwidth\)

The intensity of EMR at each wavelength region is stored separately in a stack of digital images. Each separate image is called a wavelength band or a wavelength channel.

Each band or channel can be referred to by its central wavelength value or by sequential numbering \(1, 2, 3, …\) of each band from shortest to longest wavelength

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8pY8Khf4uWjJyXddT%2Fimage.png?alt=media&token=c2946c55-5362-4ae4-9f63-be40f0bdcadc)

## Absorption Spectra and MODIS bands <a id="absorption-spectra-and-modis-bands"></a>

Sensor bands are chosen to target specific peaks in absorption spectra.

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8peveRL2YKd8qA-lk%2Fimage.png?alt=media&token=4dc7d0b5-6646-4a99-80cc-e4744dea656c)

MODIS bands

## Various pigments in algae = various peaks in absorption <a id="various-pigments-in-algae-various-peaks-in-absorption"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8poZGdGHkiCpf4vco%2Fimage.png?alt=media&token=67cf546b-f4e0-4f31-875a-2845469c7c00)

From: S. Berg, Winona State

## Spectral characteristics of oceanic waters <a id="spectral-characteristics-of-oceanic-waters"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8q8QUOlp2O2saOWW1%2Fimage.png?alt=media&token=37305520-0abc-4e85-bf28-3b1bd07a410f)

## Reminder: Higher order products <a id="reminder-higher-order-products"></a>

Example of Using Band Combinations to Make Higher Order Products

In this case making a true color image from the addition of separate R, G and B bands.

Intensity of the 8 Visible and Near-Infrared Bands from the SeaWiFS Sensor for the East Coast of the United States:

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8qJhcuwo9IKqpXqi2%2Fimage.png?alt=media&token=cfef4d15-9198-4747-8b2b-75fa3968d04c)

True-Color Image Created from bands 2, 5, and 6 corresponding to wavelengths 443, 555 and 670 nm \(+/-10 nm\)

Final Color Image = C1\*band2 + C2\*band5 + C3\*band6

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8qMyyzG78B6Aq2F1x%2Fimage.png?alt=media&token=39406d03-2446-45dd-b358-d87143de075c)

## True Color Images - VIIRS <a id="true-color-images-viirs"></a>

You can visualize or download True Color images from:

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8qf_egUGZDB8moFO3%2Fimage.png?alt=media&token=a1fcdcb6-eb93-4370-aad2-9751b4a88fd7)

Algae bloom in the east part of the Black Sea on June 3, 2012

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8qk7y5C8KwN9eipeO%2Fimage.png?alt=media&token=f617e582-a80b-4b20-92c9-4905b3a3f0fb)

Sand storm carrying sand from West Africa over Atlantic Ocean on February 27, 2015

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8qnphkvO0UQkw2ubc%2Fimage.png?alt=media&token=3789dbf5-3546-4c24-99f1-f33c2012ad38)

Vog from Kilauea Eruption, June 18, 2018

## Sunglint <a id="sunglint"></a>

Sunglint is the mirror reflection of sunlight off the sea surface.

Its signal is so much greater than the light reflected from below the surface that retrieval of information about in-water constituents by direct measurement is severely compromised, often impossible.

In regions where there is a low to moderate glint signal, it is possible to estimate the contribution of sun glint to the total signal.

For example, MODIS/Aqua crosses the equator in the early afternoon when the sun is a bit west of the sensor, and hence has sunglint issues to the west of the swath's center line, whereas MODIS/Terra has its glint region to the east of the center line because Terra crosses the equator in the late morning when the sun is a bit to the east of the sensor.

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8r1LsLrNJTtFvjo-V%2Fimage.png?alt=media&token=6dc7dd7b-8051-4a4e-b5dc-8c005ee521bf)

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8r4ZKiyOtm8z1hlI-%2Fimage.png?alt=media&token=0d3b8f07-59f3-4219-924e-ba533066d7cb)

Sunglint on a 24h VIIRS True Color image

It is not possible to estimate chlorophyll concentration where there is sunglint or clouds….

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8rFBlUKlSKSlVzMs7%2Fimage.png?alt=media&token=2f29638b-55ed-4330-b344-fd647d33111d)

Sunglint in 24h VIIRS chlorophyll-a concentration data

-&gt; need to use composites to “fill in” the gaps.

## Chlorophyll-a concentration <a id="chlorophyll-a-concentration"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8l8Wmbn_y8XZi6oct%2F-Lz8raP0735VnoQgoNLd%2Fimage.png?alt=media&token=b5c7da9c-a0d5-4793-bc11-553ff3348b07)

Chlorophyll-a concentration is estimated by looking at the ratio of different blue and green bands.

## Ocean color data products <a id="ocean-color-data-products"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8rg2LbOrTYcaUk62X%2F-Lz8rw6tgmUNZAzhAi5K%2Fimage.png?alt=media&token=71dfabbb-7397-45a8-a7b2-21b473b64d6c)

From: Jeremy Werdell, NASA

## Kd490 <a id="kd490"></a>

The diffuse attenuation coefficient in water indicates how strongly light intensity at a specified wavelength is attenuated within the water column. This parameter has wide applicability in ocean optics, as it is directly related to the presence of scattering particles in the water column, either organic or inorganic, and thus is an indication of water clarity.

The diffuse attenuation coefficient at 490 nm \(Kd490\) indicates the turbidity of the water column – i.e. how visible light in the blue to green region of the spectrum penetrates within the water column. The value of Kd490 represents the rate at which light at 490 nm is attenuated with depth.

For example a Kd490 of 0.1/meter means that light intensity will be reduced one natural log within 10 meters of water. Thus, for a Kd490 of 0.1, one attenuation length is 10 meters.

Higher Kd490 value means smaller attenuation depth, and lower clarity of ocean water.

## PAR <a id="par"></a>

The photosynthetically available radiation \(PAR\) designates the spectral range \(wave band\) of solar radiation from 400 to 700 nm that photosynthetic organisms are able to use in the process of photosynthesis.

The solar energy available for photosynthesis, known as PAR, controls the growth of phytoplankton and, therefore, the development of crustaceans, fish, and other consumers. It ultimately regulates the composition and evolution of marine ecosystems. Knowing the distribution of PAR over the oceans, spatially and temporally, is critical to understanding bio-geo-chemical cycles of carbon, nutrients, and oxygen, and to address important climate and global change issues such as the fate of anthropogenic atmospheric carbon dioxide.

For ocean color applications, PAR is a common input used in modeling marine primary productivity.

With Kd490, PAR \(& some assumptions\), we can calculate PAR at depth.

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8rg2LbOrTYcaUk62X%2F-Lz8sTHPJPIlZM2cDWyx%2Fimage.png?alt=media&token=b24d84ae-2cdb-4222-97b4-7e9bf0026522)

From: Frouin & Murakami, 2007

## Primary Productivity <a id="primary-productivity"></a>

Primary production is the rate of production of phytoplankton.•The growth requirements of phytoplankton are similar to those of any green plant: Water, Carbon dioxide, Visible light, Chemical nutrients \(nitrogen, phosphorus, ... often in short supply\)

Primary production varies with region and season, because of changes in those factors essential for phytoplankton growth. These include:

* the phytoplankton biomass
* the intensity and duration of sunshine
* the intensity of turbulence in the water
* the concentration of certain chemicals \(nutrients\) in the water
* the temperature
* the kinds of phytoplankton present.

Primary productivity can be estimated globally from chlorophyll a concentration, PAR, SST and day length.

Many different models exist. References: [http](http://www.science.oregonstate.edu/ocean.productivity/vgpm.model.php)​[://](http://www.science.oregonstate.edu/ocean.productivity/vgpm.model.php)​[www.science.oregonstate.edu/ocean.productivity/vgpm.model.php](http://www.science.oregonstate.edu/ocean.productivity/vgpm.model.php) [http://](http://www.science.oregonstate.edu/ocean.productivity/references/L&O%201997a.pdf)​[www.science.oregonstate.edu/ocean.productivity/references/L&O%201997a.pdf](http://www.science.oregonstate.edu/ocean.productivity/references/L&O%201997a.pdf) [http://](http://www.ifado.eu/wp-content/uploads/2018/08/Lobanova_etal_RemoteSensing_2018-1.pdf)​[www.ifado.eu/wp-content/uploads/2018/08/Lobanova\_etal\_RemoteSensing\_2018-1.pdf](http://www.ifado.eu/wp-content/uploads/2018/08/Lobanova_etal_RemoteSensing_2018-1.pdf)

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8rg2LbOrTYcaUk62X%2F-Lz8suWSxed339c_CK1N%2Fimage.png?alt=media&token=8e7a660b-1afa-4620-8c1f-586e80c5f79f)

ESA – May 2004, using OC-CCI data

## Phytoplankton Composition <a id="phytoplankton-composition"></a>

Satellite ocean color data is used to derive phytoplankton functional groups using a series of Remote Sensing Reflectance \(RRS\) band ratio algorithms at 490, 555 and 670 nm.

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8rg2LbOrTYcaUk62X%2F-Lz8tFNdjVTkdRW-JE4U%2Fimage.png?alt=media&token=f8b37cef-71df-40dc-b312-e27ef0cdfae6)

From: Kim Hyde and colleagues, NOAA

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8rg2LbOrTYcaUk62X%2F-Lz8tN43TFUFAQwkLMLp%2Fimage.png?alt=media&token=e1e79e85-fa4f-4a18-b47c-12c974ae9137)

## Case-1 versus Case-2 waters <a id="case-1-versus-case-2-waters"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8rg2LbOrTYcaUk62X%2F-Lz8tTLmMYIQLGXE39AY%2Fimage.png?alt=media&token=8d3670fe-c764-4b7f-bc7e-97b224dc8261)

## Optically-shallow waters <a id="optically-shallow-waters"></a>

Remotely sensed ocean color algorithms are calibrated for optically-deep waters, where the signal received by the satellite sensor originates from the water column without any bottom contribution.

Optically shallow waters are those in which light reflected off the seafloor contributes significantly to the water-leaving signal. This is known to effect geophysical variables derived by ocean-color algorithms, often leading to biased values

In the tropical Pacific, optically-deep waters are typically deeper than 15 – 30 m.

In optically-shallow waters such as lagoons, regions within atolls, and most coral reef environments, bottom substrate properties and sediment suspension may affect light propagation, which increases marine reflectance and data quality issues when quantifying in-water constituents, such as chlorophyll-a.

It is recommended to remove shallow-pixels \(&lt;30m depth\) from the study area before computing ocean color metrics.

\(Gove et al, 2013, McKinna&Werdell, 2018\)

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8rg2LbOrTYcaUk62X%2F-Lz8tdwO91no8k0nC81N%2Fimage.png?alt=media&token=6d41f21b-edac-4a5c-beab-3d75126671d9)

From: McKinna&Werdell, 2018

The Pedro Bank, a highly reflective shallow region southwest of Jamaica, and other shallow features are associated with anomalously high retrievals of chlorophyll-a concentrations.

## Global Ocean Color Sensors <a id="global-ocean-color-sensors"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8rg2LbOrTYcaUk62X%2F-Lz8tqQbuNF0rFIBES9i%2Fimage.png?alt=media&token=2842c26b-e551-47ab-a8c1-72bcb7fa07e1)

## ESA CCI <a id="esa-cci"></a>

Different sensors don’t match during their periods of overlap, making it challenging to study long-term trends.

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-WbCvoo8HH82ElCjdB%2F-M-WbLvMqbXvWmemzrVl%2Fimage.png?alt=media&token=36a95548-1825-4a19-9d5d-237eeead4418)

The European Space Agency \(ESA\) started the Climate Change Initiative \(CCI\) to generate satellite-based Essential Climate Variables to allow assessing long-term trends from satellite products.

The dataset is created by band-shifting and bias-correcting MERIS, MODIS and VIIRS data to match SeaWiFS data, merging the datasets and computing per-pixel uncertainty estimates.

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-M-WbCvoo8HH82ElCjdB%2F-M-WbHhksDGPSUSvN_Ec%2Fimage.png?alt=media&token=73cbe5d9-d127-458d-92fd-b4d9cd58fddf)

More information is available at: [http://www.esa-oceancolour-cci.org/](http://www.esa-oceancolour-cci.org/) ​

## Geostationary Ocean Color Sensors <a id="geostationary-ocean-color-sensors"></a>

All sensors in the timeline are on polar-orbiting satellites -&gt; only one observation per day \(if no clouds \)

Two geo-stationary sensors exist:

* SEVIRI \(Europe, 2004 to present – not designed for ocean color applications\)
* GOCI \(Korea, 2010 - present – dedicated to ocean color applications\)

-&gt; not very useful for Hawaii

In the US, GEO-CAPE is planned for 2022.

The principal applications of a geostationary sensor would be to:

* determine the effects of storms and tidal mixing on phytoplankton populations
* monitor biotic and abiotic material in river plumes and tidal fronts
* track hazardous materials \(e.g. oil spills and noxious algal blooms\).

This type of instrument would not provide routine global coverage as is possible from polar-orbiting, sun-synchronous satellites. However, a single imager on a geostationary satellite could provide multiple views during a single day for many locations.

\(Ruddick et al, 2014, IOCCG\)

## Ocean Color Sensors – Towards hyperspectral sensors <a id="ocean-color-sensors-towards-hyperspectral-sensors"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz8rg2LbOrTYcaUk62X%2F-Lz8upj3h88Yu8KMShma%2Fimage.png?alt=media&token=1a1097b0-c5ce-49f9-9865-dc562728aafe)

**Plankton, Aerosol, Cloud, ocean Ecosystem** \(**PACE**\) is a NASA Earth-observing satellite mission that will continue and advance observations of global ocean color, biogeochemistry, and ecology, as well as carbon cycle, aerosols and clouds. PACE data will be used to identify the extent and duration of algal blooms and improve understanding of air quality.

The satellite is planned for launch on 2 November 2022.

​

## References <a id="references"></a>

* Bruce Monger. Remote Sensing Training Program. Cornell University.
* Jeremy Werdell, NASA.
* * IOCCG 2008. Why Ocean Colour? The Societal Benefits of Ocean-Colour Technology
* Frouin & Murakami 2007. Estimating Photosynthetically Available Radiation at theOcean Surface from ADEOS-II Global Imager Data. Journal of Oceanography, Vol. 63
* Pan et al 2011. Remote sensing of phytoplankton community composition along the northeast coast of the United States. Remote Sensing of Environment 115\(12\)
* Gove et al 2013. Quantifying Climatological Ranges and Anomalies for Pacific Coral Reef Ecosystems. PLOS ONE. [https://doi.org/10.1371/journal.pone.0061974](https://doi.org/10.1371/journal.pone.0061974)​
* McKinna & Werdell 2018. Approach for identifying optically shallow pixels when processing ocean-color imagery. Opt. Express **26**, A915-A928
* * Ruddick et al 2014. Challenges and opportunities for geostationary ocean colour remote sensing of regional seas: A review of recent results. Remote Sensing of Environment. Volume 146

​

​

​

