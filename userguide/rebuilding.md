---
layout: single
title: "Rebuilding"
sidebar:
  nav: "userguide"
---
## Rebuilding on server
Whenever you add or change anything on the website, you'll need to send a 'rebuild' command to the server before your changes will go live.
1. Upload your new or revised files to the server
2. In server console (such as through PuTTY), navigate to the site's root folder
3. Run the command `bundle exec jekyll build`

## Serving locally
If you have the entire repository of the site saved locally, you can host the site locally to view your changes as you make them.  
1. In a console window, navigate to the site's root folder.
2. Run the command `bundle exec jekyll serve --incremental`
3. Open an internet browser window to the `server address` that will be provided (e.g. `http://127.0.0.1:4000/`)
4. To kill the server, return to the console window and kill the process with `ctrl-c`, and press `y` as needed to kill batch operations.
5. Remember that changes are only local; you'll need to upload them to the server and rebuild before they'll go live.

## From scratch
To rebuild the entire site afresh, in the project's root directory, run:
- `bundle exec jekyll clean`  
- `bundle exec jekyll build`  

The `/_site` folder will be cleared and repopulated with the fresh build.