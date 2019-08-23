---
layout: single
title: "Dev Notes"
sidebar:
  nav: "userguide"
---
## General Notes
### Things that must be done before deployment
- GMACS MODES and ETC applets are not included in this package, and need to be added. After they have been added, be sure to link them up on the `instruments/gmacs/` page.


### The rest
- This package doesn't include the DES Collaboration site. It's still on the server, though, if you want to keep it/add it.
- There are some extra splash images (and credits) in `/assets/splash`, maybe they need some color changes but just giving a couple options/ideas.
- In `Publications`, URLs to papers' `adsabs` page have been updated in accordance with their new database system.  
- In `Previous Team Members` page (through `People` page), please ensure that information is accurate.  
- In `Past Lab Projects`, LIGOcam does not have a page, as it did not previously have a page.  
- On `Honors and Awards` page, dead link to Ethel Ashworth-Tsutsui Memorial Award for Mentoring was excluded. (dead link: http://us.tamu.edu/2012/08/aggie-academics-invade-amsterdam/)  

- I suspect the `Reflectivity` page needs to be re-worked with new black and white studies and supporting data.  
- In `Ph.D. Degree Alumni` page, the lines `Current Position` and `Advisor`  have been omitted, as they do not yet have content on the old page. *I've left those lines commented so someone can easily add them as they become known.*  
- REU 2019 not included because I don't have any of the information.  
- I really like `/instruments/assets/LastPieceofGlass_wb.jpg` as the header image for the GMT instrument page (`/instruments/gmt`). However, they require that a proper permission request be made by contacting `info@gmto.org.`  

## Deployment
If you don't wish to deploy the site to the root directory of the web portal (http://instrumentation.tamu.edu), you'll need to change the (currently empty) `baseurl:` paraemter in `/_config.yaml`. For example, while testing previously, this was set to `baseurl: jekylltest/_site`.  
Otherwise, if you're ready to make the switch, make the `_site` folder the root directory of http://instrumentation.tamu.edu.  
**All the contents for public viewing are contained in `_site`**