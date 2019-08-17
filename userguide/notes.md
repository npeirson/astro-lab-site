---
layout: single
title: "Dev Notes"
sidebar:
  nav: "userguide"
---
## General Notes
### Things that must be done before deployment
- GMACS ETC and MODES applets are not included in this package, and **need to be added.** After they have been added, be sure to **link them up** on the `instruments/gmacs/` page.


### The rest
- There are some extra splash images (and credits) in `/assets/splash`, maybe they need some color changes but just giving a couple options/ideas.
- In `Publications`, URLs to papers' `adsabs` page have been updated in accordance with their new database system.  
- In `Previous Team Members` page (through `People` page), please ensure that information is accurate.  
- In `Past Lab Projects`, LIGOcam does not have a page, as it did not previously have a page.  
- On `Honors and Awards` page, dead link to Ethel Ashworth-Tsutsui Memorial Award for Mentoring was excluded. (dead link: http://us.tamu.edu/2012/08/aggie-academics-invade-amsterdam/)  
- On `Calendar` and `REU` pages, the Google calendars are in `iframe` blocks. This is how Google says to do it. Note that some server attacks can be performed through iframes.  

To make thing: (something not quite right tho)
<div id="overlay" onclick="off()"><div style="max-height: 80%;max-width: 80%"><img id="overlay_display"></div></div>
<script>
function on(plot) {
	document.getElementById("overlay_display").src = plot;
	document.getElementById("overlay").style.display = "block";
}

function off() {
  document.getElementById("overlay").style.display = "none";
}
</script>
<a onclick="on('../assets/disappearingGlassFish.png'); return false;" href="../assets/disappearingGlassFish.png" target="_blank">Click this to overlay</a>

- I suspect the `Reflectivity` page needs to be re-worked with new black and white studies and supporting data.  
- In `Ph.D. Degree Alumni` page, the lines `Current Position` and `Advisor`  have been omitted, as they do not yet have content on the old page. *I've left those lines commented so someone can easily add them as they become known.*  
- REU 2019 not included because I don't have any of the information.  
- I really like `/instruments/assets/LastPieceofGlass_wb.jpg` as the header image for the GMT instrument page (`/instruments/gmt`). However, they require that a proper permission request be made by contacting `info@gmto.org.  

## Deployment
If you don't wish to deploy the site to the root directory of the web portal (http://instrumentation.tamu.edu), you'll need to change the (currently empty) `baseurl:` paraemter in `/_config.yaml`. For example, while testing previously, this was set to `baseurl: jekylltest/_site`.  
Otherwise, if you're ready to make the switch, make the `_site` folder the root directory of http://instrumentation.tamu.edu.  
**All the contents for public viewing are contained in `_site`**