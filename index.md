---
title: Home | Tony Cavella
header: Tony Cavella
description: automation, infrastructure, security
permalink: /
layout: default
---
<p class="tldr">Hey, my name is Tony! I'm a Linux nerd, mobile infrastructure engineer, and general tech enthusiast!

This is my personal blog, somewhere I can write about random topics that I find interesting. That being 
said, there is no gaurentee that I will update this blog with any regular routine, mostly when I learn something 
new that I think might be beneficial to share. </p>

<h3>Blog Posts</h3>

{% for post in site.posts %}
  <p><b><a href="{{ post.url }}" class="post-title">{{ post.title }}</a></b><br>
  📅{{ post.date | date_to_string }}<br>
  {{ post.description }}</p>
{% endfor %}