---
layout: single
title: aTmCam
sidebar:
  nav: "side"
header:
  image: /instruments/assets/banner_des.jpg
toc: true
---
Story by PHYS.org available [here](https://phys.org/news/2014-10-grad-student-atmcam-cosmic-insight.html).
## Overview
The Atmospheric Transmission Monitoring Camera (aTmCam) is a new calibration system to monitor atmospheric transmission in real time, designed to enable improved photometric calibration of data acquired by large-area imaging surveys. It will be applied first to the Dark Energy Survey (DES), and hopefully to the Large Synoptic Survey Telescope in the future.

Both the atmosphere and the instruments play an important role in the photometric extinction for ground-based astronomical observation in the optical wavelengths (~300nm-1100nm). Traditional color and airmass corrections can typically achieve ~0.02 mag precision in photometric observing conditions. A major limiting factor is the variability in atmospheric throughput, which changes on timescales of less than a night.

Here, we present a way to get the atmospheric throughput in real time, by measuring the atmosphere throughput and system throughput separately. The latter one could be measured through an end-to-end spectrophotometric calibration (see DECal for more details). The atmosphere extinction is a mixing of Rayleigh scattering from molecules, aerosol and dust scattering from small particles, and molecular absorption (principally by O2, O3, and H2O). The atmospheric transmission spectrum could be easily simulated by some radiative transfer program such as [libRadTran](http://www.libradtran.org). The two figures below show the relative atmospheric transmission spectrum with different amounts of precipitable water (top) and aerosol optical thickness (bottom).

<figure>
  <img src="../assets/atmcam1.png" alt="Figure 1">
  <figcaption>Relative atmospheric transmission spectrum for varying amounts of precipitable water.</figcaption>
</figure>

<figure>
  <img src="../assets/atmcam2.png" alt="Figure 2">
  <figcaption>Relative atmospheric transmission spectrum for varying aerosol optical thickness.</figcaption>
</figure>

This simulation can also be used in reverse. We could measure the amount of each component by knowing the color pattern of the transmission curve. Therefore, we proposed the Atmospheric Transmission Monitoring Camera, or aTmCam, which uses simultaneous measurements of stars with known spectral energy distributions through a set of narrow-band filters. The filters are chosen to allow determination of specific features in the atmospheric transmission spectrum, which then can be used to develop a model that accurately represents the throughput of the atmosphere.

In 2011, we built a concept testing system to demonstrate that brightness measurements of stars at a few wavelengths can be used to derive a model for the transmission of the atmosphere that is as precise as what can be derived with spectroscopic measurements. In 2012 and 2013, we built a aTmCam prototype as a pathfinder and we deployed the prototype at Cerro Tololo Inter-American Observatory (CTIO) for ~40 nights of observing in Oct-Nov 2012 and Sept-Oct 2013 to determined the angular and temporal scale of meaningful changes in the atmosphere. After the success with the aTmCam prototype, we built and deployed a final version of aTmCam at CTIO for Dark Energy Survey (DES) in Aug 2014.

## Concept Testing
We first built a concept testing system to demonstrate that brightness measurements of stars at a few wavelengths can be used to derive a model for the transmission of the atmosphere that is as precise as what can be derived with spectroscopic measurements.

The setup for concept testing system is as follow. There are two 8-inch telescopes: one with a fiber at the focal plane that feeds an Ocean Optics JAZ spectrograph, another with an SBIG ST-402ME CCD at the focal plane. The imaging telescope has a cap on the front that holds five filters, each coupled to a "wedge prism" that diverts a ~40mm part of the pupil ~2 arcminutes. This creates five individual images on the CCD of the same star. The two telescopes are co-mounted on a tripod and are aligned to look at the same star, so we simultaneously obtain a spectrum and five narrow-band images of a star.

<figure>
  <img src="../assets/atmcam3.png" alt="Figure 3">
</figure>

We have made multiple photometric and spectroscopic measurements simultaneously with the concept testing system described above at both Texas A&M observatory and McDonald observatory. Figure below shows one of the measured atmospheric throughout (blue dots) from the observed spectra, after removal of the instrumental throughput and the stellar spectrum and best fit model (black lines) from the synthetic color indices of that measured atmospheric throughput. We conclude that the atmospheric model derived from color measurements can be an accurate representation of the true atmospheric transmission with an adequate database and a good imaging quality system.

<figure>
  <img src="../assets/atmcam4.png" alt="Figure 4">
</figure>

Read more about the Concept Testing System
- [SPIE 2012 Conference Preceeding](../assets/aTmcam_SPIE2012_Li.pdf)
- [SPIE 2012 Poster](../assets/aTmcam_SPIE2012_Li_poster.pdf)

## Prototype
After using a concept testing system to demonstrate that brightness measurements of stars at a few wavelengths can be used to derive a model for the transmission of the atmosphere, we built a prototype version of aTmCam and have used the prototype at Cerro Tololo Inter-American Observatory (CTIO) for ~40 nights of observing in Oct-Nov 2012 and Sept-Oct 2013 to determined the angular and temporal scale of meaningful changes in the atmosphere.

The aTmCam prototype consists of four Celestron f/10 8-inch telescopes mounted on two Celestron CGEM mounts. Each telescope is fitted with an SBIG ST-8300M CCD and a filter centered near a part of the spectrum sensitive to a particular component of the atmospheric throughput, with a different filter in each telescope. The figure below shows a photograph of (half of) the prototype being deployed at CTIO in October 2012.

<figure>
  <img src="../assets/atmcam5.png" alt="Figure 5">
</figure>

We have derived the precipitable water vapor (PWV) and aerosol optical depth (AOD) from the measured color of the stars using the aTmCam Prototype. We achieve a precision of ~0.6 mm of PWV and ~0.03 in AOD. We see that the precipitable water vapor can change over one night, while aerosol optical depths are generally quite stable. During our observing runs, we conclude that we need to measure the PWV only once per hour if we require PWV estimates accurate to 1mm. We also observe no significant PWV variation over an angle of ~90 degrees on the sky.

Read more about the aTmCam Prototype
- [SPIE 2014 Conference Preceeding](../assets/Li_SPIE2014_v7.pdf)
- [SPIE 2014 Poster](LI_SPIE2014_poster.pdf)

## Deployment at CTIO
After the success with the aTmCam prototype, we built and deployed a final version of aTmCam at CTIO for Dark Energy Survey (DES). It is designed to enable the improved photometric calibration of data acquired by the Dark Energy Camera (DECam) at the CTIO 4m Blanco telescope.

aTmCam is installed on the concrete pad formerly used by the "El Enano" dome. The aTmCam installation consists of a 7-foot (2.1m) diameter Astro Haven dome, a Paramount MX+ commercial telescope mount and pier, four SBIG CCDs, and four photographic camera lenses that serve as telescopes.

<figure>
  <img src="../assets/atmcam6.png" alt="Figure 6">
  <figcaption>The final system, installed at CTIO. (Photo credit: Brian Nord, Fermilab).</figcaption>
</figure>

The principle is similar to the prototype; each CCD is coupled with a narrow-band filter that monitors the brightness of suitable standard stars throughout the night. Each narrow-band filter is selected to monitor a different wavelength region of the atmospheric transmission, including regions dominated by the precipitable water vapor and aerosol optical depth. (see the figure below for the wavelength we selected.)

<figure>
  <img src="../assets/atmcam7.png" alt="Figure 7">
</figure>

The aTmCam system runs semi-autonomously. The scripted observations will be automatically initiated at the beginning of each night; the only interaction with the system from on-site personnel will be to open the dome at the beginning of the night and to close the dome at the end of the night and in case of bad weather by the telescope operators at the CTIO 4m Blanco telescope. We derive hourly atmospheric transmission models from the observations; these atmospheric transmission models will be used for the photometric calibration of Dark Energy Survey and achieve ~0.01 mag photometric precision.

**Still have questions?** Email Ting Li: sazabi@neo.tamu.edu
