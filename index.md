---
title: Home | Tony Cavella
header: Tony Cavella
description: automation, infrastructure, security
permalink: /
layout: default
---

{% for post in site.posts %}
  <p><a href="{{ post.url }}">{{ post.title }}</a><br>
  <p>{{ post.description }}<br>
  {{ post.date | date_to_string }}</p>
{% endfor %}