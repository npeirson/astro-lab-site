---
layout: single
title: "User Guide"
sidebar:
  nav: "userguide"
---
## Overview

The website uses the static site generator Jekyll. When you want to change something on the website, you'll actually be changing the source code, and then recompiling the website. This is ideal because the vast majority of laborous coding can be left to automation.

### Rebuilding

For this reason, when you go to add or change anything on the website, you'll need to send a 'rebuild' command to the server before your changes will go live.
1. Upload your new or revised files
2. Open command consol and navigate to the site's root folder
3. Run the command `bundle exec jekyll build`

### Coding

Rather than creating and editing HTML files, you'll be using Markdown ('.md') files. Markdown is a language so simple that you can learn every function in 15 minutes. [This cheatsheet has it all.](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

For our purposes, all markdown files will have two sections:
1. 'YAML Header,' much like *<head>* in HTML
2. Everything else, much like *<body>* in HTML

### Detailed User Manual

A comprehensive user manual is [available here](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/).
