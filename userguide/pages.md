---
layout: single
title: "Making New Pages"
sidebar:
  nav: "userguide"
toc: true
---
## Basics
To create a page, follow these steps:
1. Create a new markdown file with the name of your choice. For example, `mypage.md`
2. Add a header to the top of the markdown file. At minimum, this must be:
  ```
  ---
  layout: single
  title: my page title
  ---
  ```
3. Add your content anywhere below the header dashes
4. Save your new page, upload it to the server, and [rebuild the site](/userguide/)

Note: Unless otherwise specified with a [permalink](/userguide/permalinks), the name of your markdown file becomes its URL. For example, `about.md` in the root directory becomes the webpage `http://instrumentation.tamu.edu/about/`
Similarly a markdown file in a directory, like `/somefolder/example.md`, will become the webpage `http://instrumentation.tamu.edu/somefolder/example/`
## Header Options
There are many features that can be added to your page with only a few lines of code.
### Left-Side Navigation Bar
Add the following to your header:
```
sidebar:
  nav: "side"
```
Note: `"side"` refers to the sidebar named 'side' in the `_/data/navigation.yml` file. Other navigation bars can be made and used. For example, the left-side navigation bar for this user manual is named `"userguide"`, so the header for this page (without quick-nav) looks like this:
```
---
layout: single
title: "Making New Pages"
sidebar:
  nav: "userguide"
---   
```
### Right-Side Quick Nav Bar
Add the following to your header:
```
toc: true
```
The quick navigation bar is auto-populated based on the sections and subsections of the page. The title of the bar is "Quick Navigation" by default (defined in `_data/ui-text.yml`), but can be made unique to the page with a header. See the [full manual](https://mmistakes.github.io/minimal-mistakes/docs/helpers/#table-of-contents) for detailed options.
