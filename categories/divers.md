---
layout: archive
title: "Divers"
permalink: /categories/divers/
category: Divers
author_profile: false
sidebar:
  nav: "docs"
header:
  overlay_filter: rgba(0, 0, 70, 0.5)
summary: "La vie du site, les événements, les billets d'humeur..."
---

  {% for post in site.categories[page.category] %}
    {% include archive-single.html %}
  {% endfor %}
