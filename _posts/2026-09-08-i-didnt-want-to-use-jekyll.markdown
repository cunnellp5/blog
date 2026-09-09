---
layout: post
title:  "I didn't want to use jekyll"
date:   2026-09-08 16:59:32 -0600
categories: tech
---
First blog post, first time using Jekyll. I'm a fan.

Originally, my plan was to build a custom full stack app: a database for posts, a backend service to handle CRUD operations and Markdown parsing, and a minimal frontend to display the content. But every time I thought about handling image storage, rich-text editing, and safely rendering Markdown to HTML, the scope creep crept in. I had an unreasonable resistance to trying Jekyll, but here we are.

Now that the core blogging workflow is solved and I can simply write posts in .md, my next focus is media. For images, I plan to run them through Squoosh for optimization, push them to a dedicated GitHub storage repository, and serve them via jsDelivr CDN. Why? Because I dont want to pay for anything or rely on 'big-media-optimization' companies.