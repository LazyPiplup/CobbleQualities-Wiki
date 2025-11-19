---
layout: default
title: Commands
permalink: /pages/commands.html
---

{% assign grouped = site.commands | group_by: "type" | sort: "name" %}

{% for group in grouped %}
## {{ group.name }}
<div style="height:1px; background:rgba(255,255,255,0.04); margin:16px 0 24px;"></div>

<ul>
  {% assign commands_sorted = group.items | sort: "title" %}
  {% for cmd in commands_sorted %}
    <li style="display: flex; align-items: center; gap: 8px; margin-bottom: 6px;">

      {% if cmd.cmdico %}
        <img src="{{ cmd.cmdico | relative_url }}" alt="{{ cmd.title }} icon"
             style="width:24px; height:24px; image-rendering: pixelated; image-rendering: crisp-edges;">
      {% endif %}

      <a href="{{ cmd.url | relative_url }}">{{ cmd.title }}</a>
    </li>
  {% endfor %}
</ul>

{% endfor %}
