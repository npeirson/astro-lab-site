---
layout: single
title: "Image Overlays and Sliders"
sidebar:
  nav: "userguide"
toc: true
rtt: true
---
## Overlays
An image overlay is when a image file is expanded for larger viewing, occupying most of the viewport and dimming the background.  
For examples, see the [reflectance samples page](/instruments/samples/).

### Overlays by URL
Any HTML `<a>` block with a `_blank` target will overlay the image on click **if it is in `.jpg` format.** For example:  
```
<a href="/instruments/assets/BC_telescope_ad.jpg" target="_blank">
Click me
</a>
```
Produces:  
<a href="/instruments/assets/BC_telescope_ad.jpg" target="_blank">Click me</a>  

If you have multiple such references in one page, the overlay will automatically assume left and right buttons, and allow browsing the images without closing the overlay.

### Overlays by image
If you wish to allow a user to view a larger version of an image by clicking on it, simply wrap your `<img>` block with a `_blank` target `<a>` block, like so:  
```
<a href="/instruments/assets/BC_mounted_2017-01-24.jpg" target="_blank">
<img src="/instruments/assets/BC_mounted_2017-01-24.jpg"/>
</a>
```
Produces:  
<a href="/instruments/assets/BC_mounted_2017-01-24.jpg" target="_blank"><img src="/instruments/assets/BC_mounted_2017-01-24.jpg"/></a>

## Sliders
FlexSlider2 provides image gallery slider action, as on the [REU page](/pages/reu/#reu-2018). To add one to any page, simply add and customize the following code:  
```
<div class="flexslider">
  <ul class="slides">
    <li>
      <img src="/pages/assets/reu/2017/REU2017_Doyeon.jpg" />
      <p class="flex-caption">Texas A&M student Doyeon Kim with her poster</p>
    </li>
    <li>
      <img src="/pages/assets/reu/2017/REU2017_Mikayla.jpg" />
      <p class="flex-caption">Mikayla Cleaver with her poster</p>
    </li>
    <li>
      <a href="/pages/assets/reu/2017/REU2017_Ni.jpg" target="_blank">
      <img src="/pages/assets/reu/2017/REU2017_Ni.jpg" /></a>
      <p class="flex-caption">Niyousha Davachi with his poster</p>
    </li>
  </ul>
</div>
```
<div class="flexslider">
  <ul class="slides">
    <li>
      <img src="/pages/assets/reu/2017/REU2017_Doyeon.jpg" />
      <p class="flex-caption">Texas A&M student Doyeon Kim with her poster</p>
    </li>
    <li>
      <img src="/pages/assets/reu/2017/REU2017_Mikayla.jpg" />
      <p class="flex-caption">Mikayla Cleaver with her poster</p>
    </li>
    <li>
      <a href="/pages/assets/reu/2017/REU2017_Ni.jpg" target="_blank">
      <img src="/pages/assets/reu/2017/REU2017_Ni.jpg" /></a>
      <p class="flex-caption">Niyousha Davachi with his poster</p>
    </li>
  </ul>
</div>
Notice that the third slide has a `_blank` target `<a>` block surrounding the `<img>` block, thus it has both slider *and* overlay effects.  