---
title: Archive
header: Archive
description: automation, infrastructure, security
permalink: /archive
layout: default
---

### Post Archive

<div class="container text-center">
  <div class="row justify-content-sm-center row-cols-3">
  {% for post in site.posts %}
  {% assign currentdate = post.date | date: "%Y" %}
  {% if currentdate != date %}
    <div class="bg-light border-bottom" id="y{{currentdate}}">{{ currentdate }}</div>
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
    <hr/>
    <div class="d-flex justify-content-end fs-6"><a href="{{ page.url }}/#logo" class="text-uppercase fs-6 text-dark text-decoration-none">Back to Top</a></div>
    {% endunless %}
    <p class="mb-auto px-1"><h4>{{ currentdate }}</h4></p>
    {% assign date = currentdate %}
  {% endif %}
  <a href="{{ post.url }}" class="text-dark text-decoration-none mb-auto ps-1 pt-1"><h5>{{ post.title }}</h5></a>
  <p class="mb-auto px-1">{{ post.date | date_to_string }}</p>
  <p class="mb-auto px-1">{{ post.excerpt | strip_html | strip_newlines | truncate: 320 }}</p>
  {% if forloop.last %}###{% endif %}
{% endfor %}
</div>