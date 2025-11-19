---
layout: default
title: Items
permalink: /pages/items.html
---

{% assign grouped = site.items | group_by: "type" | sort: "name" %}

{% for group in grouped %}
## {{ group.name }}
<div style="height:1px; background:rgba(255,255,255,0.04); margin:16px 0 24px;"></div>

<ul>
  {% assign items_sorted = group.items | sort: "title" %}
  {% for it in items_sorted %}
    <li style="display: flex; align-items: center; gap: 8px; margin-bottom: 6px;">
      {% if it.itemico %}
        <img src="{{ it.itemico | relative_url }}" alt="{{ it.title }} icon" style="width:24px; height:24px; image-rendering: pixelated; image-rendering: crisp-edges;">
      {% endif %}

      <a href="{{ it.url | relative_url }}">{{ it.title }}</a>
    </li>
  {% endfor %}
</ul>

{% endfor %}
