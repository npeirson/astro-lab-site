---
layout: single
title: PreCal
sidebar:
  nav: "side"
rtt: true
---
<b>Nicholas Mondrik</b>  
Full documentation available [here.](/instruments/precal_docs/)  
PreCal is a monochromator based system designed to scan the throughput of commercial lenses attached to a CCD camera. The primary goal of PreCal is to measure the optical throughput of commercial lenses in the 300-900nm range. In the future, we hope to create a version of PreCal able to travel to observatories and scan their CCD-Optics system, thereby helping to reduce experimental error, and approach 1% accurate photometry. In addition, PreCal can be used to test the ability of the lens to maintain its focus over a region from white light to approx. 1000nm. Although some lenses exhibit almost no focal change, others shift drastically, which can have a significant impact on the Pixel Spread Function (PSF) of the object being imaged.  
The PreCal system consists of three major components- an OBB monochromator and monochromator controller, a calibrated photodiode, and a LABVIEW driver that manages communication with the monochromator controller, photodiode, and with the CCD-Optics system.  

<figure style="margin:auto;">
  <a href="/instruments/assets/precalFig1.jpg" target="_blank">
  <img src="/instruments/assets/precalFig1.jpg" alt="Precal setup"></a>
  <figcaption>The PreCal setup</figcaption>
</figure>

After taking data, IRAF is used to subtract the darks from their respective images, and to determine the average number of counts in each image. This is the raw throughput of the system, but since the spectrum of a Xenon arc lamp is not perfectly flat, the photodiode data must be used to decouple the Xenon emission spectrum from the data. The calibration provided with the photodiode is used to convert voltage data from the photodiode to photons/second, which reflects the amount of light at each wavelength emitted from the Xenon lamp.  
<figure style="margin:auto;">
  <img src="/instruments/assets/precalFig2.png" alt="Observed spectrum">
  <figcaption>The observed spectrum from photodiode data</figcaption>
</figure>
<figure style="margin:auto;">
  <img src="/instruments/assets/precalFig3.gif" alt="Emission spectrum from xenon arc-lamp">
  <figcaption>The emission spectrum from a Xenon arc lamp from <a href="http://www.obbcorp.com/">OBB Corporation</a></figcaption>
</figure>

By dividing the mean counts by the relative photon emission at each wavelength, the spectrum of the Xenon lamp is effectively decoupled from the data, leaving only the throughput of the CCD-optics system.  
To measure the ability of a lens to keep its focus, the CCD-optics system was fixed in place, and a 50um pinhole was placed in front of an integrating sphere. The camera was initially focused at 550nm, and its PSF at different wavelengths was measured using IRAF.  

<figure style="margin:auto;">
  <img src="/instruments/assets/PreCal_aTmCam_throughputs.png" alt="Results">
  <figcaption><a href="/instruments/assets/PreCal_aTmCam_throughputs.png" target="_blank">Click here</a> to view full size</figcaption>
</figure>

The PreCal scans of aTmCam commercial lenses and their filters. See the aTmCam page for more details. Scans were performed from 300-1000 nm in 10 nm increments for scans without a filter. Scans with a filter were performed from -50 to +50 nm from the central wavelength of the filter in 2 nm increments. Coarse scans of 10 nm steps from 300-900 nm (not shown) were performed to check for scattered light leaking into the system.  
As expected, the lenses showed excellent transmission in the visible light region, with a sharp decrease in the UV region. The gradual dropoff in the infrared region implies that the decline in transmission is likely due to failure of the anti-reflective coating on the lenses, rather than the transmission of the lens itself, since glass transmission changes tend to be sharp rises and declines, rather than gradual transitions.  
The focus experiments show that some lenses have a drastically different response to different wavelengths of light.  

<figure style="margin:auto;">
  <img src="/instruments/assets/precalFig7.png" alt="Throughputs">
  <figcaption>A focus test performed on the 500mm and 300mm Mamiya lenses. The PSF is measured as the Full Width Half Maximum (FWHM) of a 50um pinhole at 10m</figcaption>
</figure>

The above figure demonstrates the focal changes for different lenses. Although both lenses achieve a comparable PSF at their focus wavelength (550nm), the 500mm lens rapidly deviates from this focus starting at roughly 50nm away from the focal wavelength. The evolution of the PSF is as follows:  

<figure style="margin:auto;">
  <img src="/instruments/assets/precalFig8.png" alt="500mm lens @ 400nm ">
  <figcaption>500mm lens @ 400nm </figcaption>
</figure>
<figure style="margin:auto;">
  <img src="/instruments/assets/precalFig9.png" alt="500mm lens @ 550nm ">
  <figcaption>500mm lens @ 550nm </figcaption>
</figure>
<figure style="margin:auto;">
  <img src="/instruments/assets/precalFig10.png" alt="500mm lens @ 700nm">
  <figcaption>500mm lens @ 700nm</figcaption>
</figure>

Thus, when white light, such as a star is imaged through the lens, the PSF is a superposition of all of these states, and those in between, weighted by the relative throughput of the wavelength. This means that most of the 550nm (+/- 50nm) light is centered, but the shorter and longer wavelengths form an outer structure to the image.  
In conclusion, we see that commercial lenses exhibit good transmission through the visible light and into the infrared region. In fact, the lack of transmission in the infrared region is likely due to failure in the anti-reflective coating, rather than the optical properties of the glass itself, and of the three tests on three different lenses, this trend was the same. However, of the two lenses whose focus was tested, one rapidly diverged from a small PSF to form ring-like rather than spot-like structures, while the other maintained a spot-like structure throughout all wavelengths. Thus, when observing a source of white light such as a star, for the 500mm lens (the poor one) a structure forms that is the superposition of all structures, while for the 300mm lens (the good one) a very tight structure should be maintained. This means that the 300mm lens should be able to achieve a better PSF than the 500mm lens.  