---
title: "All Categories"
layout: archive
permalink: /categories/
author_profile: true
entries_layout: list
---

{% comment %}
Build a combined hash of categories including both blog posts and portfolio items
{% endcomment %}

{% assign all_docs = site.posts | concat: site.portfolio %}
{% assign category_map = "" | split: "" %}

{% for doc in all_docs %}
{% for cat in doc.categories %}
{% assign key = cat | downcase %}
{% if category_map contains key %}
{% assign index = category_map | index_of: key %}
{% assign updated = category_map[index][1] | push: doc %}
{% assign category_map = category_map | where_exp: "c", "c[0] != key" %}
{% assign category_map = category_map | push: [key, updated] %}
{% else %}
{% assign category_map = category_map | push: [key, [doc]] %}
{% endif %}
{% endfor %}
{% endfor %}

{% include posts-taxonomy.html taxonomies=category_map %}
