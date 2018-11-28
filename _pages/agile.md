---
title: "Agile"
sitemap: true
layout: collection
permalink: /agile/
collection: agile
entries_layout: grid
classes: wide
---

Esta sección está dedicada al mundo Agile.

<ul>
<p>Post más recientes</p>
  {% for post in site.posts %}
    {% if post.categories contains 'Agile' %}
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endif %}
  {% endfor %}
</ul>