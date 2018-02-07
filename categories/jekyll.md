---
layout: archive
title: "Jekyll"
permalink: /categories/jekyll/
category: Jekyll
author_profile: false
sidebar:
  nav: "jekyll"
header:
    overlay_image: /assets/images/bandeau_lichens.jpg
summary: "Tous les billets concernant *Jekyll*, le générateur de sites statiques diffusé par Github..."  
---

{% for post in site.categories[page.category] %}
  {% include archive-single.html %}
{% endfor %}
