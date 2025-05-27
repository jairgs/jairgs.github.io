---
title: "All Categories"
layout: archive
permalink: /categories/
author_profile: true
entries_layout: list
---

{% comment %}
Collect all unique categories from posts and portfolio
{% endcomment %}

{% assign posts = site.posts %}
{% assign portfolio = site.portfolio %}

{% assign post_cats = posts | map: "categories" | join: "," | split: "," %}
{% assign port_cats = portfolio | map: "categories" | join: "," | split: "," %}

{% assign all_cats = post_cats | concat: port_cats | uniq | sort %}

<ul class="taxonomy__index">
  {% for cat in all_cats %}
    {% assign count_posts = site.posts | where_exp: "p", "p.categories contains cat" | size %}
    {% assign count_portfolio = site.portfolio | where_exp: "p", "p.categories contains cat" | size %}
    {% assign total = count_posts | plus: count_portfolio %}
    <li><a href="#{{ cat | slugify }}"><strong>{{ cat }}</strong> <span class="taxonomy__count">{{ total }}</span></a></li>
  {% endfor %}
</ul>

{% for cat in all_cats %}

  <section id="{{ cat | slugify }}" class="taxonomy__section">
    <h2 class="archive__subtitle">{{ cat }}</h2>
    <div class="entries-{{ page.entries_layout | default: 'list' }}">
      {% assign docs = site.posts | concat: site.portfolio %}
      {% assign filtered = docs | where_exp: "doc", "doc.categories contains cat" %}
      {% for doc in filtered %}
        {% include archive-single.html type=page.entries_layout post=doc %}
      {% endfor %}
    </div>
    <a href="#page-title" class="back-to-top">{{ site.data.ui-text[site.locale].back_to_top | default: "Back to Top" }} &uarr;</a>
  </section>
{% endfor %}
