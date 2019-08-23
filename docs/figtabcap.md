---
layout: single
title: "Figures, Captions, and Tables"
sidebar:
  nav: "userguide"
toc: true
---
You can add figures, tables, images, and captions to your page content using either Markdown or HTML notation. In fact, even advanced HTML commands can be used in your .md page file's content to get as fancy as you'd like.

## Figures
I'd recommend using the following LaTeX-like snippet for adding figures:
```
<figure>
  <a href="/instruments/assets/gmacs-ms.jpg" target="_blank">
  <img src="/instruments/assets/gmacs-ms.jpg"></a>
  <figcaption>Figure 3: The GMACS-MS interface with a DSS image.</figcaption>
</figure>
```
<figure>
  <a href="/instruments/assets/gmacs-ms.jpg" target="_blank">
  <img src="/instruments/assets/gmacs-ms.jpg"></a>
  <figcaption>Figure 3: The GMACS-MS interface with a DSS image.</figcaption>
</figure>

## Tables
Markdown's approach to tables is similar to that of LaTeX. There are also [table generators](https://www.tablesgenerator.com/markdown_tables) available for markdown. You can read more on the [markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#tables).  
Here's their example:
```
| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| column 3 is      | right-aligned | $1600 |
| column 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
```

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| column 3 is      | right-aligned | $1600 |
| column 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

Or, if you prefer good ol' HTML tables, that'll work too.