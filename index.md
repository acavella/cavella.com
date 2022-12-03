---
title: Home
header: Tony Cavella
description: automation, infrastructure, security
permalink: /
layout: default
---
{% for post in site.posts %}
<div class="col-md-12">
  <div class="row g-0 border rounded overflow-hidden flex-md-row mb-4 shadow-sm h-md-250 position-relative">
    <div class="col p-8 d-flex flex-column position-static">
      <a href="{{ post.url }}" class="text-dark text-decoration-none mb-auto ps-1 pt-1"><h5>{{ post.title }}</h5></a>
      <p class="mb-auto px-1">{{ post.excerpt | strip_html | strip_newlines | truncate: 650 }}</p>
      <a href="{{ post.url }}" class="card-link text-secondary mb-auto ps-1">READ MORE</a>
    </div>
    <div class="col-auto d-none d-lg-block">
    {% if post.thumbnail %}
      <img src="{{ post.thumbnail }}" class="img-fluid" style="width: 200px; height: 200px; object-fit: cover;" alt="Responsive image">
    {% else %}
      <img src="/assets/images/placeholder-square.png" class="img-fluid" style="width: 200px; height: 200px; object-fit: cover;" alt="Responsive image">
    {% endif %}
    </div>
    <div class="card-footer bg-light d-flex bd-highlight">
      <div class="me-auto bd-highlight"><svg class="bi" width="16" height="16"><use xlink:href="#calendar"/></svg><small class="text-muted"> {{ post.date | date_to_string }}</small></div>
      <div class="bd-highlight"><small class="text-muted">{{ post.category }} <svg class="bi" width="16" height="16"><use xlink:href="#tag"/></svg></small></div>
    </div>
  </div>
</div>
<br>
{% endfor %}