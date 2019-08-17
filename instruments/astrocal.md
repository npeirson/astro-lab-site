---
layout: single
title: Astrocal
sidebar:
  nav: "side"
header:
  image: /instruments/assets/banner_des.jpg
---
**Daniel Freeman**

A standard system for telescope transmission observing and calibration (Astrocal) is a spectrophotometric calibration system used on 0.4 meter to 4 meter telescopes in the 300nm to 1100nm range.

Astrocal is intended to be used on all telescopes used for a follow up on the data Large Synoptic Sky Survey Telescope (LSST) will be gathering. If multiple telescope are used for this they must be calibrated to a common photometry scale, so they can be compared to the data produced by a single telescope.

Astrocal works fundamentally the same as [DECal.](/instruments/decal/) Like DECal, Astrocal consists of seven major components: a light source; monochromator; spectrometer; fiber bundle; projectors; photodiodes; and a lambertian screen, Figure 1.

<figure>
  <a href="/instruments/assets/DeCal_layout.png" target="_blank"><img src="/instruments/assets/DeCal_layout.png" alt="DECal Layout"></a>
  <figcaption>Figure 1: a systems diagram of DECal<sup>[1]</sup> and Astrocal. The light source provides light to the monochromator. The monochromater mechanically selects a specific wavelength of light. The light is carried by the fiber optic cable, and evenly projected through engineered diffusers onto a lambertian screen. Photodiodes mounted around the top of the telescope see the light being bounced off the lambertian screen. The amount of light seen by the photodiodes is compared to the amount of light seen by the CCD in the telescope. The relative throughput of the telescope can be determined from this.</figcaption>
</figure>

## Research
The biggest challenge with making DECal mobile, stems from the wide variety of telescopes it would be calibrating. To get an idea of what Astrocal would face in the real world, a list of 22 telescopes to research was made. These telescopes were chosen because they are candidates for calibration once Astrocal is complete. Research on these telescopes focused on aspects of their design that would influence Astrocal's mounting system, and projection pattern. These criteria include: Primary mirror diameter; secondary mirror diameter; f/#; dome clearance; and if the telescope is made out of a material that a magnetic mount could attach to, like steel, Figure 2.

<figure>
  <a href="/instruments/assets/telescopes.PNG" target="_blank"><img src="/instruments/assets/telescopes.PNG" alt="Telescopes Researched"></a>
  <figcaption>Figure 2: Telescopes Researched</figcaption>
</figure>

In addition to the research on telescopes, research was conducted on improving the individual components of DECal, and reusing components from precal. The most important of these was the light source. DECal's light source used two separate lamps, this was done because neither could cover the 300nm to 1100nm range. The 75 watt was used from 300nm to 700nm, and the quartz was used from 700nm to 1100nm. The new light source, an EQ-99X<sup>[2]</sup>, can cover the whole range and it is brighter than the previous light sources. This increase in brightness is important because it allows us to take shorter exposer times, due to the photodiodes and the telescope seeing more light in a given timeframe. This will shorten the overall length of time needed to perform a calibration.

The main component that will be adapted from precal is the monochromator. The monochromator used on precal is a version that can only have one light source mounted to it at a time. While this would be a problem for DECal, Astrocal only uses one light source so this isn't a problem.

## Dome clearance
One of the design parameters for Astrocal is the distance between the top of a telescope to the dome wall Figures 2 and 3. This is important because the engineered diffusers need distance to spread to their target diameter. If there was just one projector the target diameter would be the diameter of the lambertian screen. The labertian screen is the same diameter as the primary mirror. The dome clearance was determined by looking at pictures of the telescopes and comparing the diameter of the telescope to the distance between the front of the telescope and the dome. This method, while relatively inaccurate, allowed us to find outliers.

In order to evenly project light onto the lambertian screen diffusers have to be used. Diffusers take light and project it in a cone at a set angle. The diffusers we chose are polymer on glass engineered diffusers from RPC Photonics<sup>[3]</sup>. Diffusers come in angles ranging from half a degree to 120 degrees. It was determined that diffusers with different angles could be used to alter the necessary dome clearance for a given telescope. The number of projectors used can also alter the clearance needed. More projectors require less clearance because they don't need to spread out to as large of a diameter. Figure 3 shows the patterns for different numbers of projectors.

<figure>
  <a href="/instruments/assets/projectionpattern.PNG" target="_blank"><img src="/instruments/assets/projectionpattern.PNG" alt="Projection Pattern"></a>
  <figcaption>Figure 3: Projection Pattern<sup>[4]</sup></figcaption>
</figure>

To determine what angle of diffuser should be used with a given telescope and number of projectors, the telescopes were plotted on a primary mirror diameter vs dome clearance graph. Lines that mark the minimum distance needed for a diffuser to reach its target diameter were also plotted, Figures 4 and 5.

If a telescope falls over a line it has more than the necessary dome clearance. If it falls under a line it has less than the necessary clearance. Any telescope that falls under the widest angle diffuser will need to mount its lambertian screen externally to get the appropriate clearance.

<figure>
  <a href="/instruments/assets/fourprojectors.PNG" target="_blank"><img src="/instruments/assets/fourprojectors.PNG" alt="Figure Four"></a>
  <figcaption>Figure 4: Primary Mirror Diameter vs Dome Clearance for a four projector system</figcaption>
</figure>

<figure>
  <a href="/instruments/assets/oneprojectergraph.PNG" target="_blank"><img src="/instruments/assets/oneprojectergraph.PNG" alt="Figure Five"></a>
  <figcaption>Figure 5: Primary Mirror Diameter vs Dome Clearance for a single projector system</figcaption>
</figure>

Some telescopes will need to mount their screens externally due to their dome clearance or the shape of their dome. Skymapper is a good example of this. Skymapper is the telescope that falls below the maximum angled diffuser for both graphs. Skymapper's dome clearance is 4cm, as visible in Figure 6.


<figure>
  <a href="/instruments/assets/skymapper.jpg" target="_blank"><img src="/instruments/assets/skymapper.jpg" alt="Skymapper"></a>
  <figcaption>Figure 6: Skymapper</figcaption>
</figure>

## Fiber Optic Cable

The fiber optic cable used in Astrocal is a 75 meter fiber bundle consisting of 35 300 micron cores. This number of cores was chosen based on the height of the exit slit of the monochromater, and 35 cores is less than half of the 87 used in DECal. This provides significant cost savings. These cores would be arranged in a single row. The fiber bundle would separate at 65 meters into four fibers with eight cores each. The remaining three cores would branch off at the ferrule and be 75 meters long like the other branches. This branch would connect with the spectrometer.

In addition to the fiber bundle itself, some thought was given to how the bundle connects to the monochromator. The main problem with the fiber port currently on the monochromator is how inconsistent it is. The fiber ferrule is held in by eight set screws in an aluminum rectangular tube. Its inconsistency stems from the possibility that some of the screws would push the ferrule off-center. In addition to getting less light, the wavelength of light slightly left or right of a slit is different than at the center. Figures 7 and 8 show a more consistent port that doesn't use set screws.

<figure style="width:335px">
  <a href="/instruments/assets/FerrulePortPlate.jpg" target="_blank"><img src="/instruments/assets/FerrulePortPlate.jpg" alt="Ferrule Port Plate"></a>
  <figcaption>Figure 7: Ferrule Port Plate</figcaption>
</figure>
<div class="clearfix" />
<figure>
  <a href="/instruments/assets/FiberFerrule.jpg" target="_blank"><img src="/instruments/assets/FiberFerrule.jpg" alt="Fiber Ferrule"></a>
  <figcaption>Figure 8: Fiber Ferrule</figcaption>
</figure>

The plate bolts to the exit slit of the monochromator. The fiber ferrule connects to the plate via two bolts.

<a href="../assets/DanielFreemanAstrocal_Poster.pdf" target="_blank">Click here</a> to view the Astrocal poster.

## References
<ul>
  <li>
    <small>[1] : Jean-Philippe Rheault, D. L. DePoy, J. L. Marshall, T. Prochaska, R. Allen, J. Wise, E. Martin. (2012) <a href="../assets/DECal_Fermilab2012_Marshall.pdf" target="_blank">"DECal: A Spectrophotometric Calibration System For DECam"</a></small>
  </li>
  <li>
    <small>[2] : Energetiq. <a href="http://www.energetiq.com/ldls-laser-driven-light-source-duv-broadband.php" target="_blank">EQ-99X LDLS.</a></small>
  </li>
  <li>
    <small>[3] : RPC Photonics. <a href="http://www.rpcphotonics.com/engineered-diffusers-information/" target="_blank">Engineered Diffusers.</a></small>
  </li>
  <li>
    <small>[4] : <a href="http://www2.stetson.edu/~efriedma/circovcir/" target="_blank">Circles Covering Circles,</a> Erich's Packing Center.</small>
  </li>
</ul>