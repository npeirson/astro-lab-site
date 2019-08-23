---
layout: single
title: "User Guide"
sidebar:
  nav: "userguide"
---
## Introduction
In addition to a visual overhaul, there are loads of new features just beneath the surface, which serve to improve user experience. While browsing the site, don't just look at it; click around, and you'll see these features emerge.

## The docs / user manual
To view properly, serve the site to yourself and view the docs rendered. Otherwise, some things won't display, including the sidebar. For that reason, if you need to read this without serving the site, here are more links the other pages:  
- [Making New Pages](pages.html)  
- [Making New Press Releases](posts.html)  
- [Figures, Tables, Captions](figtabcap.html)  
- [Image Overlays and Sliders](imagestuff.html)  
- [Rebuilding](rebuilding.html)  
- [Rolling Developer's Notes](notes.html) 


## Overview
This website uses the static site generator Jekyll. When you want to change something, you'll need to recompile the website after making changes to the source code. This is ideal because the vast majority of laborous coding can be left to automation. Although this is intended to make it easier to design new pages, you'll need to know the syntax, which spans six or seven programming languages. It's easy, I promise.

### Important to Understand
The **entire project's** root folder *is not* the same as the **site's** root folder. When the entire project is built, the output---which resides in `/_site`---is the **site's** root folder, and contains all content necessary for site operation. Changes to the site are made to the content in the **project's** root directory, but **http://instrumentation.tamu.edu** should point specifically to the `_site` folder.  
To be clear: do not make content alterations within the `_site` folder---allow it to be populated programmatically. Instead, make your changes/additions to the content in the other folders, which will become built into `_site`.

## Rebuilding the site
After any changes are made, the site must be rebuilt before they will become live. Please follow [these instructions](/docs/rebuilding/).

## The Markdown thing
Pages are written as Markdown files (suffix `.md`), but contain YAML headers, and can contain Markdown or HTML content. Markdown is much easier than HTML, as you'll soon see.  

### Markdown Cheatsheet
The language you can learn in 45 seconds. [Click here for the cheat-sheet.](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

## Base Theme User Manual
The base theme user manual is [available here](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/).