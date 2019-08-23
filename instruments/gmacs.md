---
layout: single
title: GMACS
sidebar:
  nav: "side"
toc: true
header:
  image: /instruments/assets/Banner_GMACS.jpg
rtt: true
---
The Giant Magellan Telescope Multi-object Astronomical and Cosmological Spectrograph (GMACS) is a wide field, multi-object, moderate-resolution, optical spectrograph being designed for the Giant Magellan Telescope (GMT). Our goal is to create an instrument capable of spectroscopically observing the faintest possible targets, which are currently known only from imaging observations. High throughput, simultaneous wide wavelength coverage, accurate and precise sky subtraction, moderate resolution, relatively wide field, and substantial multiplexing are crucial design drivers for the instrument.  
## Software & Tools
- [GMACS Mask Simulator](/instruments/gmacs-ms/)
- [GMACS Exposure Time Calculator](/)  
- [GMACS Configurations Explorer](/)  

## Current Development
<figure>
  <a href="/instruments/assets/split-labeled.jpg" target="_blank"><img src="/instruments/assets/split-labeled.jpg" alt="GMACS Assembly"></a>
  <figcaption>Figure 1: The current GMACS concept. After the field lens the light is spit into red and blue channels. The VPH gratings and camera assemblies can rotate independently of each other (up to 90° camera-collimator angle). Masks or the MANIFEST fiber interface are exchanged using a cassette system at the top of the instrument (see Fig. 2).</figcaption>
</figure>

SPIE 2018 papers and posters:  
- [GMACS Overview Paper](/publications/assets/2018-SPIE-10702-069_paper.pdf)
- [Mechanical Design Paper](/publications/assets/2018-SPIE-10702-364-Optomechanical_paper.pdf), [Mechanical Design Poster](/publications/assets/2018-SPIE-10702-364-Optomechanical_poster.pdf)
- [Optical Design Paper](/publications/assets/2018-SPIE-10702-340-Optical_Design_paper.pdf), [Optical Design Poster](/publications/assets/2018-SPIE-10702-340-Optical_poster.pdf)
- [Electrical Design Paper](/publications/assets/2018-SPIE-10702-365-Electronics_paper.pdf), [Electrical Design Poster](/publications/assets/2018-SPIE-10702-365-Electronics_poster.pdf)
- [Systems Engineering Paper](/publications/assets/2018-SPIE-10705-046-SE_paper.pdf), [Systems Engineering Poster](/publications/assets/2018-SPIE-10705-046-SE_poster.pdf)

The current concept for GMACS includes ≥20 interchangeable multi-object slit masks which are placed at the focal plane of the GMT. After passing through a field lens, a dichroic splits the beam into “blue” (reflected) and “red” (transmitted) channels split at 558nm. Each channel has a collimating lens group followed by exchangeable VPH gratings. The light is then focused onto each red or blue optimized CCD array (8k x 12k pixels) via f/2.2 cameras. The positions of the optical assemblies are controlled with an active flexure compensation system. As the telescope tracks an object, this system responds to the changing gravity vector, removing flexure induced image motion. GMACS will also contain a wavelength calibration system and cameras for target acquisition and mask alignment.

<figure>
	<a href="/instruments/assets/smem-labeled.jpg" target="_blank"><img src="/instruments/assets/smem-labeled.jpg"></a>
	<figcaption>
		Figure 2: Concept for the slit mask exchange mechanism. Masks are loaded into a magazine and can be inserted into the focal plane via the slit mask elevator. Surrounding the focal plane are multiple guide, acquisition, and focus cameras that are used to align target objecs with their respective slits as well as provide focus offsets to the GMT Acquisition, Guiding, and Wavefront Sensing system (AGWS). On the opposite side of the focal plane, the MANIFEST fiber positioner interface is shown. It can be inserted into the focal plane using the same rail system as the slit masks.
	</figcaption>
</figure>

Key design parameters are summarized in the table below.

| Parameter | Requirement / Goal | Comments |
| :------------- |:-------------:| -------------:|
| Field of View | 30 arcmin sq. / 50 arcmin sq. |  |
| Wavelength Coverage | 350-950nm / 320-1000nm |  |
| Spectral Resolution | Blue: 1000-6000 <br />Red: 1000-6000 | 0.7” slit width,<br />full coverage at lower resolutions,<br />wavelength coverage at higher resolutions is sacrificed |
| Image Quality | 0.30 / 0.15 arcsec | 80% EE, tied to MANIFEST fiber diameter |
| Spectral Stability | 0.3 / 0.1 | spectral resolution elements per hour |
| Grating Exchange | 1 / ≥2 gratings | multiple wavelength regions |
| Slit Mask Exchange | 12 / ≥20 | cassette-style mask changer |

## How GMACS fits into the GMT
GMACS will be mounted in the Gregorian Instrument Rotator as shown in the figure below. The instrument design will also include handling and test carts to facilitate assembly, integration and verification of the instrument, as well as instrument exchange at the telescope.
<figure>
  <a href="/instruments/assets/gmacs_in_telescope_v2.jpg" target="_blank"><img src="/instruments/assets/gmacs_in_telescope_v2.jpg" alt="GMACS in Telescope"></a>
  <figcaption>Figure 3: GMACS will be mounted in the Gregorian Instrument Rotator.</figcaption>
</figure>

## History
Due to a generous contribution from George P. Mitchell '40 in 2004, Texas A&M was named a founding partner in the Giant Magellan Telescope. The GMT, to be constructed in northern Chile, will be the largest telescope on earth and produce images up to ten times clearer than the Hubble Space Telescope. 

In 2011, Mr. Mitchell and the Mitchell Foundation committed a landmark gift of $25 million to the project, $12.5 million of which will be pledged on behalf of Texas A&M. This gift brings Mitchell's total commitment to the GMT project on behalf of the university to over $21 million, furthering his goal to keep TAMU Physics and Astronomy on the forefront of scientific innovation and discovery.

In 2015, the Texas A&M University System Board of Regents continued Mitchell's legacy by reaffirming Texas A&M University's support for GMT and pledging to fund Texas A&M's participation in the project as a significant partner.

More information about the Giant Magellan Telescope can be found at the [GMT Website.](http://www.gmto.org/)

GMACS has a long history of design studies and active collaboration with GMT partner institutions, in the form of instrument software development by Korean collaborators (S. Pak), mechanical design planning from partners in Brazil (K. Taylor), optical design studies by Carnegie (S. Shectman and R. Bernstein), and project management provided by C. Froning at UT-Austin.

A GMACS community workshop during 2014 March 18-19 at Texas A&M University helped to define the scientific requirements for the instrument. The workshop included 51 participants, representing all of the GMT partners and including representatives from national and international non-partners. The participants provided expertise in a wide range of astrophysical areas through contributed talks and breakout groups focused on (1) stars, star-formation, and planets; (2) resolved Galaxies (including Dwarf Galaxies) and near-field cosmology; and (3) distant galaxies (including reionization and first light science). Past design studies, requirements from GMTO and input from the scientific community have been condensed into key design requirements and formal instrument development has begun. An advantage of the instrument history is that most technical risks to the project are well known and most have well-considered mitigation strategies (i.e. appropriate detectors, optics blanks, lens fabrication vendors, etc. are identified or commercially available).

Click to read the [Conceptual Design Report](/instruments/assets/GMACS_CoDR_Report_web.pdf) for the previous iteration of GMACS.

## Student led projects related to GMACS  
- [Cargille Test](/instruments/cargille/)  
- [MooSci](/instruments/moosci/)  
- [GMACS Mask Simulator](/instruments/gmacs-ms/)  

For more information on GMACS and the GMT, please visit our [Publications page.](/publications/)
