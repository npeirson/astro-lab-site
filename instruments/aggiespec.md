---
layout: single
title: AggieSpec
sidebar:
  nav: "side"
---
<b>An Instrument for the 1.54m Telescope at the Astronomical Observatory of Córdoba</b>  
The Department of Physics and Astronomy at Texas A&M University is currently in the process of building AggieSpec, a low resolution spectrograph for the 1.54m telescope at the Astronomical Observatory of Córdoba in Argentina. This instrument is required to cover a broad wavelength range (4000Å < λ < 9000Å) at a resolution of R = λ/Δλ ~ 500 to 1000, allowing its use as a versatile astronomical spectrograph. Such an instrument would allow the 1.54m telescope to be used for a variety of research projects including identification of quasi-stellar objects (QSO's) and identifying spectral types of variable stars. The telescope's location in the southern hemisphere enables spectroscopic follow-up of objects found in several large scale imaging surveys such as the Dark Energy Survey (DES) and Large Synoptic Survey Telescope (LSST).

<figure style="margin:auto;">
  <img src="../assets/aggiespec_prototype.jpg" alt="AggieSpec prototype">
  <figcaption>A photograph of the prototype of AggieSpec using two Nikon lenses as collimator and camera, a 300 line/mm Shimadzu grating for dispersion, and a SBIG-8300M CCD as a detector. Together, these off-the-shelf components produce an R ~ 500 spectrograph with wavelength coverage of 4000Å to 8000Å.</figcaption>
</figure>

AggieSpec uses off-the-shelf lenses, gratings, and a CCD system to reduce the cost and the complexity of the spectrograph. The grating is produced by Shimadzu; we foresee a system where the gratings are interchangeable, allowing AggieSpec to achieve a higher resolution at the expense of simultaneous wavelength coverage. Using a 300 line/mm grating and a 2 arcsecond fiber (70 microns), we achieve a R ~500 spectrograph with a wavelength coverage of 4000Å to 8000Å. We expect to have a high resolution mode using a 600 line/mm grating, enabling R ~ 1000 and coverage of 5000Å to 7000Å. 
The collimator is a 200mm focal length, f/4 Nikon lens; the camera is a 135mm focal length f/2 Nikon lens. Both lenses were originally designed for 35mm photography, but using the PreCal system in the lab, we have demonstrated that Nikon lenses have adequate throughput and image quality to be used in astronomical instrumentation.

<figure style="margin:auto;">
  <img src="../assets/ThroughputTests.jpg" alt="AggieSpec throughput">
  <figcaption>Throughput of 200mm focal length, f/4 Nikon lens (points) and relative throughput of a similar lens measured with the <a href="../precal/">PreCal system</a> <a href="../../publications/Conceptual design of a low resolution spectrograph for the Astronomical Observatory of Cordoba - Nagasawa et al.pdf">(Nagasawa et al. 2014)</a>.</figcaption>
</figure>

AggieSpec will be composed of three modules:  
- The Acquisition and Guide Module which will be mounted onto the telescope and contain the guiding camera and two fibers (one for the science target and one for sky subtraction) that will carry light to the spectrograph  
- The Calibration Module which will house the calibration lamps and fiber feed light from the lamps to the spectrograph module. This module will be on an optical bench.  
- The Spectrograph Module which will house the collimator, grating, camera, and detectors. This module will be on an optical bench.  