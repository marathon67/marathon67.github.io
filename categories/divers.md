---
layout: archive
title: "Divers"
permalink: /categories/divers/
category: Divers
author_profile: false
sidebar:
  nav: "docs"
header:
  overlay_image: /assets/images/bandeau_mousses.jpg
summary: "La vie du site, les événements, les billets d'humeur..."
---

  {% for post in site.categories[page.category] %}
    {% include archive-single.html %}
  {% endfor %}
