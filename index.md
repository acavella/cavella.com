---
title: Home | Tony Cavella
header: Tony Cavella
description: automation, infrastructure, security
permalink: /
layout: default
---
<p>Hey, my name is Tony! Welcome to my personal blog/site. I will attempt to update this regularly, however, 
I make no guarantee. I work in the mobile security and infrastructure; mostly test, evaluation and integration. 
I'm also building a large homelab using primarily large clusters of Raspberry Pis, much of my writing will 
document that journey.

{% for post in site.posts %}
  <p><a href="{{ post.url }}">{{ post.title }}</a><br>
  {{ post.description }}<br>
  {{ post.date | date_to_string }}</p>
{% endfor %}