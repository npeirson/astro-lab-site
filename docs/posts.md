---
layout: single
title: "Making New Posts"
sidebar:
  nav: "userguide"
toc: true
---
## Basics  
To make a press release, follow these steps:  
1. In the `_posts` folder, create a new markdown file using simple date format `YYYY-MM-DD-postname.md`
2. Include a YAML header:
  ```
  ---
  title: time dilation through excessive caffeine
  ---
  ```
3. Add your content below the header.
4. Save your new page, and [rebuild the site](/docs/rebuilding/)

## Categories and Tags  
For a variety of archiving features like categories, related reading recommendations, and search functions, it's advisable to include categories and tags. These are added to your header like so:
```
---
title: Example News Story
categories:
  - Interviews
tags:
  - gmt
  - gmacs
  - etc
---
```

## Example Post  
As an example, the press release post for the eclipse is a markdown file titled `2017-08-22-eclipse-success.md`, and contains the following code:
```
---
title: "Solar Eclipse Viewing Event: Success"
categories:
  - outreach
tags:
  - social
  - eclipse
---
The partial solar eclipse viewing event was a success! Hundreds of people joined Professor Darren DePoy, Dr. Luke Schmidt and the members of the Star Party team in Rudder Plaza. Read more about solar eclipse and the event on [The Eagle](http://www.theeagle.com/news/local/science-community-mingle-during-eclipse-viewing-party-at-texas-a/article_24a68c34-fe2e-5a5a-bfdb-0ef4f97bf200.html) and [The Battalion!](http://www.thebatt.com/science-technology/community-comes-together-to-witness-rare-solar-eclipse/article_05b43fd2-87aa-11e7-84ac-1330d0dd54f1.html)
```

Located in the `_posts` folder, this file build into [this press release](/outreach/eclipse-success/), and becomes automatically chronologically listed on the [press page](/press/).  

The `/press/` folder contains two additional pages, permalinked to `/tags/` and `/categories/`, which sorts listings by such. Presently there are no links pointing to them, so they are lonely pages, and available if you want them.

## Categories/Tags Pages
Dedicated tags and categories pages are automatically generated. The word clouds are an implementation of [jQCloud](https://mistic100.github.io/jQCloud/). Custom layouts `default-archive` feed unique js/css to layouts `archive`, which are the basis of layouts `categories` and `tags`. This is where you can change the cloud parameters (colors, size, shape, etc). Permalinked pages `categories.md` and `tags.md` therefore automatically populate their contents, including word cloud form (based on frequency of tag/category). Note that the only exception to this is the cloud's link hover colors, which are defined in `/assets/css/jqcloud.min.css`. 