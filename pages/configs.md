---
layout: default
title: Configs
permalink: /pages/configs.html
---

{% assign grouped = site.configs | group_by: "type" | sort: "name" %}

{% for group in grouped %}
## {{ group.name }}
<div style="height:1px; background:rgba(255,255,255,0.04); margin:16px 0 24px;"></div>

<ul>
  {% assign configs_sorted = group.items | sort: "title" %}
  {% for cnfg in configs_sorted %}
    <li style="display: flex; align-items: center; gap: 8px; margin-bottom: 6px;">

      {% if cnfg.cnfgico %}
        <img src="{{ cnfg.cnfgico | relative_url }}" alt="{{ cnfg.title }} icon"
             style="width:24px; height:24px; image-rendering: pixelated; image-rendering: crisp-edges;">
      {% endif %}

      <a href="{{ cnfg.url | relative_url }}">{{ cnfg.title }}</a>
    </li>
  {% endfor %}
</ul>

{% endfor %}
