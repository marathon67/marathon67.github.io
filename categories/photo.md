---
layout: archive
title: "Photo"
permalink: /categories/photo/
category: Photo
author_profile: false
sidebar:
  nav: "docs"
---

{% for post in site.categories[page.category] %}
  {% include archive-single.html %}
{% endfor %}
