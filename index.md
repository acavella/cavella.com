---
title: Home
header: Tony Cavella
description: automation, infrastructure, security
permalink: /
layout: default
---
<div class="container col-xxl-8 px-4 py-5">
  <div class="row flex-lg-row-reverse align-items-center g-5 py-5">
    <div class="col-10 col-sm-8 col-lg-6">
        <img src="/assets/images/tc-profile2.jpg" class="d-block mx-lg-auto img-fluid" alt="Bootstrap Themes" width="700" height="500" loading="lazy">
    </div>
    <div class="col-lg-6">
        <h1 class="display-5 fw-bold lh-1 mb-3">Responsive left-aligned hero with image</h1>
        <p class="lead">Quickly design and customize responsive mobile-first sites with Bootstrap, the world’s most popular front-end open source toolkit, featuring Sass variables and mixins, responsive grid system, extensive prebuilt components, and powerful JavaScript plugins.</p>
    </div>
  </div>
</div>
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