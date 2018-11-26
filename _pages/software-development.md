---
title: "Desarrollo de Software"
sitemap: true
layout: collection
permalink: /software-development/
collection: development
entries_layout: grid
classes: wide
---

Esta sección está dedicada al Desarrollo de Software. 

<ul>
  {% for post in site.categories.development %}
    {% if post.url %}
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endif %}
  {% endfor %}
</ul>