---
share: true
links:
  mdlinks: false
  convert: true
filename: 2023-01-11-jekyll-workflow-with-obsidian
layout: post
title: "Improving my Jekyll Workflow with Obsidian"
date: 2023-01-11
category: News
---

I'm bounced around on various blogs over the years and have learned one thing, if the publishing workflow is complicated or cumbersome, you are less likely to write.  When considering a CMS like Wordpress, Ghost or Drupal, the have excellent WYSIWYG editors built-in that contribute to a simple writing and editing workflow. On the other hand I find the do everything nature of these platforms contributes to their large overhead and general overcomplexity. For this reason, I tend to gravitate to the lightweight simplicity of static site generators such as Jekyll (and similar).  

After a few iterations, I have a pretty sustainable workflow using Jekyll. All of my Jekyll source is hosted on a [Github](https://github.com/acavella/cavella.com) repository. From there it is built, updated and deployed using [Netlify](https://netlify.com). Netlify wraps this all in a neat little bow providing fast hosting using my own custom domains and even provides me a free TLS certificate through [Lets Encrypt](https://letsencrypt.org). 

![[../assets/images/jekyll-workflow.drawio.png|jekyll-workflow.drawio.png]]

Unfortunately, this workflow is still missing the simplicity provided by a WYSIWYG editor. 