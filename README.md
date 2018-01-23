# Jekyll + MinimalMistakes + Elbow Grease = AIL
## Adding pages
Individual pages are added as markdown files. They need only have a header referencing a layout in /\_layouts, and a title.
```
---
layout: single
title: Page Title
---
My content
```
Other objects such as sidebars can be added as simply as:
```
---
layout: single
title: Page Title
sidebar:
  nav: "side"
---
```
Pages are automatically assigned a URL. For example, `/about.md` automatically hosts as `website.com/about/`  
and `/instruments/index.html` is automatically assigned `website.com/instruments/`  
URLs can also be manually hardcoded regardless of their location in the directory structure. For example,  
```
---
layout: single
title: Page Title
permalink: /whatever/
---
```  
A header like this would define its URL as `website.com/whatever/` even if the `whatever.md` file is buried somewhere like `/assets/js/vendor/jquery/whatever.md`.

## Adding press releases
Articles added to the Press page are also markdown files, with a simple header and content:
```
---
title: "Time Dilation through Excessive Caffeine"
---
Article content
```
They need only be named according to the simple date-based naming convention `YYYY-MM-DD-whatever.md` and dropped into the `_posts` folder. Everything else is automatic.

## List Objects
The sidebar and header lists can be edited in `_data/navigation.yml` very easily:
```
side:
    - title: Instruments
      url: /instruments/
      children:
        - title: Giant Magellan Telescope
          url: /instruments/gmt/
          kiddos:
          - title: "GMACS"
            url: /instruments/gmacs/
```

## Figures and Tables
Adding figures and tables is HTML but very similar to LaTeX:
```
<figure>
  <img src="image.jpg">
  <figcaption>Figure 1: A picture</figcaption>
</figure>
```
