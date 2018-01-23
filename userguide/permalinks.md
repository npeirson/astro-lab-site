---
layout: single
title: "Permalinks"
sidebar:
  nav: "userguide"
---
## Overview
You can use permalinks to assign your page a fixed url, no matter where the markdown file lives.

To demonstrate this, I'll use the press release about the success of the eclipse event, which lives at:  
`http://instrumentation.tamu.edu/outreach/eclipse-success/`

In order to keep it as a part of the *press releases* page and archive, it must remain in the `_posts` folder. However, suppose you wanted to direct people to this post during a presentation and wanted to simplify the URL, you can do this with a permalink.

Simply adding `permalink: /eclipse/` to your post header will make it accessable at `http://instrumentation.tamu.edu/eclipse/`
