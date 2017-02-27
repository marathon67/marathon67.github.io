---
layout: archive
title: "Jekyll"
permalink: /categories/jekyll/
category: Jekyll
author_profile: false
sidebar:
  nav: "jekyll"
header:
    overlay_filter: rgba(0, 20, 120, 0.5)
summary: "Tous les billets sur *Jekyll*, le générateur de sites statiques diffusé par Github..."  
---

{% for post in site.categories[page.category] %}
  {% include archive-single.html %}
{% endfor %}
