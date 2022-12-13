---
title: Archive
header: Archive
description: automation, infrastructure, security
permalink: /archive
layout: default
---
<div class="container justify-content-center">
  <div class="row">
    <div class="col-10">
      {% for post in site.posts %}
      {% assign currentdate = post.date | date: "%Y" %}
      {% if currentdate != date %}
      {% unless forloop.first %}
        <hr class="mb-0">
        <div class="d-flex justify-content-end">
          <small><a href="{{ page.url }}/#archive-menu" class="text-uppercase text-dark text-decoration-none">Back to Top ↑</a></small>
        </div>
      {% endunless %}
        <p class="mb-auto px-1" id="y{{ currentdate }}"><h4>{{ currentdate }}</h4></p>
      {% assign date = currentdate %}
      {% endif %}
        <p class="mb-auto px-1 h5"><a href="{{ post.url }}" class="text-dark text-decoration-none mb-auto">{{ post.title }}</a></p>
        <p class="mb-auto px-1">{{ post.date | date_to_string }}</p>
        <p class="mb-auto px-1 pb-3">{{ post.excerpt | strip_html | strip_newlines | truncate: 320 }}</p>
      {% if forloop.last %}
        <div class="d-flex justify-content-end">
          <small><a href="{{ page.url }}/#archive-menu" class="text-uppercase text-dark text-decoration-none">Back to Top ↑</a></small>
        </div>
      {% endif %}
      {% endfor %}
    </div>
    <div class="col-2" id="archive-menu">
      <div class="row justify-content-sm-left row-cols-1">
        {% for post in site.posts %}
        {% assign currentdate = post.date | date: "%Y" %}
        {% if currentdate != date %}
        <div class="p-2 bg-light border">
          <a href="{{ page.url }}/#y{{ currentdate }}" class="text-uppercase fs-6 text-dark">{{ currentdate }}</a>
        </div>
        {% assign date = currentdate %} 
        {% endif %}
        {% endfor %}
      </div>
    </div>
  </div>
</div>




