---
layout: single
title: GMACS
sidebar:
  nav: "side"
toc: true
---
The Giant Magellan Telescope Multi-object Astronomical and Cosmological Spectrograph (GMACS) is a wide field, multi-object, moderate-resolution, optical spectrograph being designed for the Giant Magellan Telescope (GMT). Our goal is to create an instrument capable of spectroscopically observing the faintest possible targets, which are currently known only from imaging observations. High throughput, simultaneous wide wavelength coverage, accurate and precise sky subtraction, moderate resolution, relatively wide field, and substantial multiplexing are crucial design drivers for the instrument.

## Current Development
<figure>
  <img src="../assets/gmacs_assembly.jpg" alt="GMACS Assembly">
  <figcaption>Figure 1: The current GMACS concept. The VPH gratings and camera assemblies can rotate independently of each other (90° range of motion). Masks are exchanged using a cassette system at the top of the instrument.</figcaption>
</figure>
[GMACS structure and optics arrangement concepts](../assets/GMACS-structure-and-optics-arrangement-concepts.pdf)

SPIE 2016 papers and posters:
- [Mechanical design paper](../assets/2016 SPIE 9908-375 - Optomechanical design concept for GMACS - paper.pdf)
- [Mechanical design poster](../assets/2016 SPIE 9908-375 - Optomechanical design concept for GMACS - poster.pdf)
- [Optical design paper](../assets/2016 SPIE 9908-376 - Optical design concept for GMACS - paper.pdf)
- [Optical design poster](../assets/2016 SPIE 9908-376 - Optical design concept for GMACS - poster.pdf)

The current concept for GMACS includes ≥20 interchangeable multi-object slit masks which are placed at the focal plane of the GMT. After passing through a field lens and collimator lens group, a dichroic splits the beam into “blue” (reflected) and “red” (transmitted) channels split at around 600nm. Exchangeable VPH gratings disperse the light which is then focused onto each red or blue optimized CCD array (8k x 12k pixels) via camera lens groups, again optimized for each wavelength range. The position of the camera optical assembly is controlled with an active flexure control system. As the telescope tracks an object, this system responds to the changing gravity vector, removing flexure induced image motion. GMACS will also contain an internal wavelength calibration system and cameras for target acquisition and mask alignment.

Key design parameters are summarized in the table below.

| Parameter | Requirement / Goal | Comments |
| :------------- |:-------------:| -------------:|
| Field of View | 30 arcmin sq. / 50 arcmin sq. |  |
| Wavelength Coverage | 350-950nm / 320-1000nm |  |
| Spectral Resolution | Blue: 1000-6000 <br />Red: 1000-6000 | 0.7” slit width,<br />full coverage at lower resolutions,<br />wavelength coverage at higher resolutions is sacrificed |
| Image Quality | 0.30 / 0.15 arcsec | 80% EE |
| Spectral Stability | 0.3 / 0.1 | spectral resolution elements per hour |
| Grating Exchange | 1 / ≥2 gratings | multiple wavelength regions |
| Slit Mask Exchange | 12 / ≥20 | cassette-style mask changer |

Click to use the GMACS exposure time calculator and view the GMACS trade studies.

## How GMACS fits into the GMT
GMACS will be mounted in the Gregorian Instrument Rotator as shown in the figure below. The instrument design will also include handling and test carts to facilitate assembly, integration and verification of the instrument, as well as instrument exchange at the telescope.
<figure>
  <img src="../assets/gmacs_in_telescope.jpg" alt="GMACS in Telescope">
  <figcaption>Figure 2: GMACS will be mounted in the Gregorian Instrument Rotator.</figcaption>
</figure>

## GMACS-MS
The GMACS Mask Simulator (GMACS-MS) is a slit mask design and visualization program for GMACS. GMACS-MS is a plug-in for ESO Skycat, a catalog and .fits viewer. It is a modified version of OSMOS Mask Simulator<sup>1</sup> (OMS). Skycat is known to run on Linux and MacOS X. During development, GMS was tested using a virtual machine running Fedora 14 and is currently the only confirmed working platform. A screenshot displaying several of GMS's features is shown below.

<figure>
  <img src="../assets/gmacs-ms.jpg" alt="GMACS-MS">
  <figcaption>Figure 3: The GMACS-MS interface with a DSS image and GSC-2 catalog loaded.</figcaption>
</figure>

Shown above, the cyan rectangle is the CCD footprint of the GMACS detector, and the white circle is the boundary of the instrument focal plane. After an image is loaded, a custom or online catalog can be initialized and create the various ellipses shown on the field which mark object locations. Using the 'Auto-Slit' function, shown in the drop-down menu above, creates the slits as shown above. When saved, the program outputs three files which can be used for manufacturing, visualization, and cross-checking of the mask template with expectations. As the underlying framework of GMS remains the same as OMS and the earlier LUCI Mask Simulator (LMS), a detailed overview of features can be found in the LMS User Manual<sup>2</sup>.

[Download it here](../assets/GMS_001.zip)  
[Presentation](../assets/GMACS Mask Simulator.pdf)  
[<sup>1</sup> OMS User's Manual](http://www.astronomy.ohio-state.edu/~martini/osmos/oms.html)  
[<sup>2</sup> LMS User Manual](http://abell.as.arizona.edu/~lbtsci/Instruments/LUCIFER/Documents/LMS_UserManual_v160.pdf)  

## History
GMACS has a long history of design studies and active collaboration with GMT partner institutions, in the form of instrument software development by Korean collaborators (S. Pak), mechanical design planning from partners in Brazil (K. Taylor), optical design studies by Carnegie (S. Shectman and R. Bernstein), and project management provided by C. Froning at UT-Austin.

A GMACS community workshop during 2014 March 18-19 at Texas A&M University helped to define the scientific requirements for the instrument. The workshop included 51 participants, representing all of the GMT partners and including representatives from national and international non-partners. The participants provided expertise in a wide range of astrophysical areas through contributed talks and breakout groups focused on (1) stars, star-formation, and planets; (2) resolved Galaxies (including Dwarf Galaxies) and near-field cosmology; and (3) distant galaxies (including reionization and first light science). Past design studies, requirements from GMTO and input from the scientific community have been condensed into key design requirements and formal instrument development has begun. An advantage of the instrument history is that most technical risks to the project are well known and most have well-considered mitigation strategies (i.e. appropriate detectors, optics blanks, lens fabrication vendors, etc. are identified or commercially available).

Click to read the [Conceptual Design Report](../assets/GMACS_CoDR_Report_web.pdf) for the previous iteration of GMACS.

For more information on GMACS and the GMT, please visit our <a href="../../publications/">Publications</a> page.
