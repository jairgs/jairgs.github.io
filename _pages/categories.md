---
title: "Portfolio by Category"
permalink: /portfolio/categories/
layout: single
author_profile: true
---

<h2>Portfolio Categories</h2>
<ul>
  {% assign all_cats = site.portfolio | map: "categories" | join: "," | split: "," | uniq | sort %}
  {% for cat in all_cats %}
    <li>
      <a href="/portfolio/category/{{ cat | downcase | url_encode }}/">
        {{ cat | capitalize }}
      </a>
    </li>
  {% endfor %}
</ul>
