---
title: Archive
header: Archive
description: automation, infrastructure, security
permalink: /archive
layout: default
---

### Post Archive

<div class="container text-center"  id="archive-menu">
  <div class="row justify-content-sm-center row-cols-3">
  {% for post in site.posts %}
  {% assign currentdate = post.date | date: "%Y" %}
  {% if currentdate != date %}
    <div class="p-2 bg-light border"><a href="{{ page.url }}/#y{{currentdate}}" class="text-uppercase fs-6 text-dark text-decoration-none">{{ currentdate }}</a></div>
  {% assign date = currentdate %} 
  {% endif %}
  {% endfor %}
  </div>
</div>

<div class="col-md-12">
{% for post in site.posts %}
  {% assign currentdate = post.date | date: "%Y" %}
  {% if currentdate != date %}
    {% unless forloop.first %}
    <div class="d-flex justify-content-end fs-6"><hr/><a href="{{ page.url }}/#archive-menu" class="text-uppercase fs-6 text-dark text-decoration-none">Back to Top ↑</a></div>
    {% endunless %}
    <p class="mb-auto px-1" id="y{{currentdate}}"><h4>{{ currentdate }}</h4></p>
    {% assign date = currentdate %}
  {% endif %}
  <a href="{{ post.url }}" class="text-dark text-decoration-none mb-auto ps-1 pt-1"><h5>{{ post.title }}</h5></a>
  <p class="mb-auto px-1">{{ post.date | date_to_string }}</p>
  <p class="mb-auto px-1">{{ post.excerpt | strip_html | strip_newlines | truncate: 320 }}</p>
  {% if forloop.last %}
    <div class="d-flex justify-content-end fs-6"><a href="{{ page.url }}/#archive-menu" class="text-uppercase fs-6 text-dark text-decoration-none">Back to Top ↑</a></div>
  {% endif %}
{% endfor %}
</div>