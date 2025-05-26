---
title: "Portfolio by Category"
permalink: /portfolio/categories/
layout: archvie
author_profile: true
---

{% assign all_cats = post_cats | concat: port_cats | uniq | sort %}

<ul>
  {% for cat in all_cats %}
    {% assign port_count = site.portfolio | where_exp: "p", "p.categories contains cat" | size %}
    {% assign total = post_count | plus: port_count %}
    <li>
      <a href="/categories/{{ cat | downcase | url_encode }}/">{{ cat }}</a> ({{ total }})
    </li>
  {% endfor %}
</ul>
