---
title: Simple.css - A classless CSS framework
header: Simple.css {}
description: A classless CSS framework that makes semantic HTML look good.
permalink: /
layout: default
---

{% for post in site.posts %}
  <p><a href="{{ post.url }}">{{ post.title }}</a><br>
  {{ post.description }}<br>
  {{ post.date | date_to_string }}</p>
{% endfor %}