---
layout: archive
title: "Jekyll"
permalink: /categories/jekyll/
category: Jekyll
author_profile: false
sidebar:
  nav: "docs"
---

{% for post in site.categories[page.category] %}
  {% include archive-single.html %}
{% endfor %}
