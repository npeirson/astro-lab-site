---
layout: single
title: "Adding Pages"
sidebar:
  nav: "userguide"
toc: true
rtt: true
---
1. Create your new page as a markdown file
2. Add a header
3. Add your content
4. Upload and recompile

## Where they go
- If you create a new `something.md` file in the root directory, it will compile to `http://instrumentation.tamu.edu/something/`.  
- The same effect can be achieved by creating a new folder (e.g. `this_folder/`) in the root directory, then adding an `index.md` file to it. `/this_folder/index.md` would compile, just as before, to `http://instrumentation.tamu.edu/this_folder/`  
- Other html files in a subfolder (such as `this_folder`) will assume similar structure. For example, `/this_folder/another_page.md` would compile to `http://instrumention.tamu.edu/this_folder/another_page/`.  
- These assignments can be overridden by including a `permalink` in a page's header. For example,
  ```
  ---
  layout: single
  title: "Example page"
  permalink: /specific_place/
  ---
  ```
  would compile the page to `http://instrumenttion.tamu.edu/specific_place/` *no matter where the page file resides in the source code.*  
- Be aware that any files and folders with the prefix `_` such as `_layouts` are only used in compilation, and do not exist in the published site.  

## Header
Headers, which preceed all else in a page markdown file, must have at minimum a layout specified. E.g.:  
```
---
layout: single
---
```

### Layout
There are several page layouts, but they are for purposes like the splash page, archives, etc --- you're welcome to check them out in `_layouts`.  
In the vast majority of cases, you'll probably be looking to add pages using the `single.html` layout.

### Title
The `title` parameter becomes the header-1 (`<h1>`) block at the top of the compiled page. For example, in this very page's `.md` file, the header contains `title: "Adding pages"`, the result of which is the page's header at the very top.

### Header image
Header images can be added to any page by including the following in the header:  
```
header:
  image: /path_to/my_image.jpg
```

### Sidebar navigation
The optional left-side navigation bar can be included in a page by adding the following to header:  
```
sidebar:
  nav: "my-sidebar"
```
The contents of the sidebar (in this case, `my-sidebar`) is defined in `/_data/navigation.yml`. A quick look in that file will make it pretty clear how to add or change sidebars.

### Table of Contents
The optional right-side table-of-contents can be enabled by adding the following to header:
```
toc: true
```
The table of contents is automatically populated by any headers 2 and 3 (i.e. `##` and `###` in Markdown, `<h2>` and `<h3>` in HTML) within the page.  
Note: if you use the TOC on a page with HTML format headers, you will need to include a unique `id` in order to link the TOC target to the header's section. For example: `<h2 id="section2">Section 2</h2>` If the `id` parameter is left blank, the section header will be displayed in the TOC, but will not be targetted thereby. An example of this can be found in the `pages/phdalumni.md` file.

### Return-to-Top button
The Return-to-Top button is a small round button which glides along the bottom right of any `layout: single` page's content frame, which allows the user to clickly (that's a quick click) return to the top of the page. You can find it toward the bottom right of this very page. It can be added to your page by including the following in page header:
```
rtt: true
```  
The CSS for this is in `/_sass/_page.scss`, the JS is in `/_includes/rtt.html`, and the HTML is in `/_layouts/single.html`.

### Permalinks
As aforementioned, a page's specific location in the site file-structure can be hard-coded regardless of the page file's actual location. For example, `/some_folder/some_page.md` would normally compile to `http://instrumentation.tamu.edu/some_folder/some_page/`, but the header clause `permalink: /mighty_page/` would cause it to compile to `http://instrumentation.tamu.edu/mighty_page/` despite the markdown file's actual position in the file-structure.

## Content
Your page's content will be everything following the header. For example:
```
---
layout: single
title: "Example page"
rtt: true
---
This is my content!
```
The content can be entered as Markdown or HTML. Markdown is easier, but HTML may be necessary for advanced formatting.  
Note that Markdown can contain HTML, but HTML cannot contain Markdown; if you open an HTML object of any kind (e.g. `<div>`, `<a>`,`<i>`), you cannot use Markdown again until it has been closed. For example:  
- `## <a href="www.google.com">Google</a>` will result in a header-2 (`<h2>`) block with hyperlink text 'Google' directing to the referenced URL. HTML can exist within Markdown.
- `<h2>[Google](www.google.com)</h2>` will result in a useless mess, despite appearing to have the same components. Markdown cannot exist within HTML.
- There are occasional exceptions to this, but don't count on them.

## Upload and Rebuild
Please see the detailed [rebuilding](/userguide/rebuilding/) document.

## Note about the homepage
Assets for the home page (splash page) go in `/assets/front/`. The featured content is described in the **YAML header** of `/index.html` Images should be `640x360`.