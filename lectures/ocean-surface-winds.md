# Ocean Surface Winds

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz9IqY8KU5G9VeCCE5w%2F-Lz9JE4jMHF9-mjE3sU8%2Fimage.png?alt=media&token=f3aabd7b-8f62-4743-babd-92bc1e3282ac)

QuikSCAT, 01/03/2004

This lecture is also available as part of an audio-narrated [PowerPoint presentation](https://oceanwatch.pifsc.noaa.gov/files/hawaii2020/05-Salinity-Winds-Altimetry.pptx).

Ocean wind is defined as the motion of the atmosphere relative to the surface of the ocean.

Typically, ocean winds are measured very close to the ocean surface by buoys, platforms, and ships. The most common reference height for near-surface ocean wind measurements is **10 meters above sea level**. Satellite ocean wind measurements are done **using both passive and active instruments.**

Today, the combination of all available satellite wind measurements can provide **global coverage** over the ice-free oceans at **multiple times per day.**

Sensors operate at microwave frequencies -&gt; can make measurements day and night and under nearly all-weather conditions.

Both active \(radar scatterometers\) and passive \(radiometers\) microwave instruments are capable of retrieving the ocean surface wind speed.

Active microwave instruments are also capable of retrieving the wind direction.

Microwave measurements are inaccurate in regions of heavy rain and close to coasts.

Typical spatial resolution is ~ 25km.

## Passive sensors – basic principle <a id="passive-sensors-basic-principle"></a>

The ocean surface responds quickly to the motion of the air above, which provides a distinct **roughness** pattern depending on the relative speed and direction of the wind with respect to the ocean surface.

The roughness of the ocean surface provides a specific “**brightness**” which can only be observed using passive microwave radiometers;

With the right combination of specific microwave wavelengths and processing algorithms, the brightness of the ocean surface can be accurately translated to a near-surface wind speed.

## Active sensors – basic principle <a id="active-sensors-basic-principle"></a>

Scatterometry uses surface roughness and pulse angle to get wind direction and speed.

The backscatter of scatterometer pulses is sensitive to sea surface roughness, which can be translated to **wind speed** \(see above\).

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz9KbOXdhtTMGpMnukl%2F-Lz9jnmc9-fRaP6V6oov%2Fimage.png?alt=media&token=a59547b7-a8b3-49e9-8a7f-d41b60259d81)

The backscatter is also sensitive to the pulse direction relative to the **wind direction.**

For any wind speed, the backscatter returned to the sensor is - maximal with the pulse pointed upwind - minimal with the pulse pointed crosswind

Problem: A suite of speeds and directions could explain a single measurement.

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz9KbOXdhtTMGpMnukl%2F-Lz9kMQtwoPMEdp7n2Aa%2Fimage.png?alt=media&token=5c138dc4-c0e8-4263-b6b6-cb63a02a268c)

Solution: - Measure backscatter at several pulse directions. - Then solve for the wind speed and direction that best fits all of the measurements.

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz9KbOXdhtTMGpMnukl%2F-Lz9kmp8SoTWntQnNHvr%2Fimage.png?alt=media&token=65c5b4bc-26ff-4069-aee7-bd7fd96267ed)

## Ocean Surface Winds - sensors <a id="ocean-surface-winds-sensors"></a>

![](https://gblobscdn.gitbook.com/assets%2F-LylLNCSXaUER_FiqDSx%2F-Lz9KbOXdhtTMGpMnukl%2F-Lz9ks6RruFSxhoCAQ69%2Fimage.png?alt=media&token=e73cf657-7de4-42d6-9628-9011eb0b6ba8)

From: http://www.remss.com/measurements/ccmp/

## CCMP <a id="ccmp"></a>

The Cross-Calibrated Multi-Platform \(CCMP\) gridded surface vector winds are produced using satellite, moored buoy, and model wind data, and as such, are considered to be a Level-4 ocean vector wind analysis product.

The V2.0 CCMP processing now combines Version-7 RSS radiometer wind speeds, QuikSCAT and ASCAT scatterometer wind vectors, moored buoy wind data, and ERA-Interim model wind fields using a Variational Analysis Method \(VAM\) to produce four maps daily of 0.25 degree gridded vector winds.

Data is provided every 6 hours, and as monthly composites.

Spatial resolution is 0.25º

From 1987 – present.

## Wind stress & Wind stress curl <a id="wind-stress-and-wind-stress-curl"></a>

**Wind stress** is the shear stress exerted by the wind on the surface of the ocean. It is the force component parallel to the surface, per unit area, as applied by the wind on the water surface.

**Wind stress curl** is a measure of the rotation of wind: curl = dv/dx - du/dy In the northern hemisphere, positive curl is associated with upwelling of water, negative curl with downwelling.

Wind stress and wind stress curl are available for QuikSCAT and ASCAT data

## References <a id="references"></a>

​[https://sos.noaa.gov/datasets/ocean-surface-winds/](https://sos.noaa.gov/datasets/ocean-surface-winds/) [https://podaac.jpl.nasa.gov/OceanWind](https://podaac.jpl.nasa.gov/OceanWind) [http://www.remss.com/measurements/ccmp/](http://www.remss.com/measurements/ccmp/)

