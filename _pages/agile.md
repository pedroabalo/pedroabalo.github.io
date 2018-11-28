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
  {% for post in site.posts %}
  <p>{{ post.categories }}</p>
    {% if post.categories contains "agile" %}
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endif %}
  {% endfor %}
</ul>