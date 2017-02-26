---
layout: archive
title: "Photo"
permalink: /categories/photo/
category: Photo
author_profile: false
sidebar:
  nav: "docs"
header:
  overlay_filter: rgba(0, 70, 0, 0.5)
summary: "Les billets sur la *photo augmentée* : stacking, panoramique, haute définition zoomable..."
---

{% for post in site.categories[page.category] %}
  {% include archive-single.html %}
{% endfor %}
