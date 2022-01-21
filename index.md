---
title: Home | Tony Cavella
header: Tony Cavella
description: automation, infrastructure, security
permalink: /
layout: default
---
<p class="tldr">Hey, my name is Tony! I'm a Linux nerd, mobile infrastructure engineer, and general tech enthusiast! This is my personal blog, somewhere to share my personal thoughts and projects. There is no gaurentee that I will update this blog with any regularity, but will try my best to post content I find interesting.</p>

<h3>Blog Posts</h3>

{% for post in site.posts %}
  <p><a href="{{ post.url }}" class="post-title">{{ post.title }}</a><br>
  📅{{ post.date | date_to_string }}<br>
  {{ post.description }}</p>
{% endfor %}