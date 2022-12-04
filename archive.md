---
title: Archive
header: Archive
description: automation, infrastructure, security
permalink: /archive
layout: default
---
<div class="col-md-12">
{% for post in site.posts %}
  {% assign currentdate = post.date | date: "%Y" %}
  {% if currentdate != date %}
    {% unless forloop.first %}
    <div class="d-flex justify-content-end"><a href="{{ page.url }}/#logo" class="text-dark text-decoration-none mb-auto ps-1 pt-1">Back to Top</a></div>
    <hr/>
    {% endunless %}
    <p class="mb-auto px-1"><h3>{{ currentdate }}</h3></p>
    {% assign date = currentdate %}
  {% endif %}
  <a href="{{ post.url }}" class="text-dark text-decoration-none mb-auto ps-1 pt-1"><h5>{{ post.title }}</h5></a>
  <p class="mb-auto px-1">{{ post.date | date_to_string }}</p>
  <p class="mb-auto px-1">{{ post.excerpt | strip_html | strip_newlines | truncate: 320 }}</p>
  {% if forloop.last %}###{% endif %}
{% endfor %}
</div>