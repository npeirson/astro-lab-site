---
layout: single
title: "GMACS-MS"
sidebar:
  nav: "side"
header:
  image: /instruments/assets/Banner_GMACS.jpg
---
The GMACS Mask Simulator (GMACS-MS) is a slit mask design and visualization program for GMACS. GMACS-MS is a plug-in for ESO Skycat, a catalog and .fits viewer. It is a modified version of OSMOS Mask Simulator [1] (OMS). Skycat is known to run on Linux and MacOS X. During development, GMS was tested using a virtual machine running Fedora 14 and is currently the only confirmed working platform. A screenshot displaying several of GMS's features is shown below.

<figure>
  <img src="/instruments/assets/gmacs-ms.jpg" alt="GMACS-MS">
  <figcaption>Figure 1: The GMACS-MS interface with a DSS image and GSC-2 catalog loaded.</figcaption>
</figure>

Shown above, the cyan rectangle is the CCD footprint of the GMACS detector, and the white circle is the boundary of the instrument focal plane. After an image is loaded, a custom or online catalog can be initialized and create the various ellipses shown on the field which mark object locations. Using the 'Auto-Slit' function, shown in the drop-down menu above, creates the slits as shown above. When saved, the program outputs three files which can be used for manufacturing, visualization, and cross-checking of the mask template with expectations. As the underlying framework of GMS remains the same as OMS and the earlier LUCI Mask Simulator (LMS), a detailed overview of features can be found in the LMS User Manual [2].

### Documents and Downloads
- [Download GMAC-MS](/instruments/assets/GMS_001.zip)
- [GMACS-MS PDF](/instruments/assets/GMACS Mask Simulator.pdf)
- [OMS User Manual](http://www.astronomy.ohio-state.edu/~martini/osmos/oms.html)
- [LMS User Manual](http://abell.as.arizona.edu/~lbtsci/Instruments/LUCIFER/Documents/LMS_UserManual_v160.pdf)
