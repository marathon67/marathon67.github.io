---
layout: archive
title: "Photo"
permalink: /categories/photo/
category: Photo
author_profile: false
sidebar:
  nav: "pictures"
header:
  overlay_filter: rgba(0, 70, 0, 0.5)
summary: "Et surtout *photo augmentée* : stacking, panoramas, haute définition zoomable..."
---

{% for post in site.categories[page.category] %}
  {% include archive-single.html %}
{% endfor %}
