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

<div class="blog-index">  
    <ul>
        {% for category in site.categories %}
        <li><a name="{{ category | first }}">{{ category | first }}</a>
            <ul>
            {% for post in category.last %}
            <li><a href="{{ post.url }}">{{ post.title }}</a></li>
            {% endfor %}
            </ul>
        </li>
        {% endfor %}
    </ul>
</div>