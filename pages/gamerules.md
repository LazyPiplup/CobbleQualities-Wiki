---
layout: default
title: Gamerules
permalink: /pages/gamerules.html
---

{% assign grouped = site.gamerules | group_by: "type" | sort: "name" %}

{% for group in grouped %}
## {{ group.name }}
<div style="height:1px; background:rgba(255,255,255,0.04); margin:16px 0 24px;"></div>

<ul>
  {% assign gamerules_sorted = group.items | sort: "title" %}
  {% for gr in gamerules_sorted %}
    <li style="display: flex; align-items: center; gap: 8px; margin-bottom: 6px;">

      {% if gr.grico %}
        <img src="{{ gr.grico | relative_url }}" alt="{{ gr.title }} icon"
             style="width:24px; height:24px; image-rendering: pixelated; image-rendering: crisp-edges;">
      {% endif %}

      <a href="{{ gr.url | relative_url }}">{{ gr.title }}</a>
    </li>
  {% endfor %}
</ul>

{% endfor %}
