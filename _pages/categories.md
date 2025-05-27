---
title: "All Categories"
layout: archive
permalink: /categories/
author_profile: true
entries_layout: list
---

{% comment %}
Ensure both collections exist and are arrays (avoid concat crash in Jekyll 3)
{% endcomment %}

{% assign posts = site.posts %}
{% assign portfolio = site.portfolio %}

{% unless posts %}
{% assign posts = "" | split: "" %}
{% endunless %}

{% unless portfolio %}
{% assign portfolio = "" | split: "" %}
{% endunless %}

{% assign all_docs = posts | concat: portfolio %}

{% comment %}
Build a category-to-docs map manually
{% endcomment %}
{% assign categories_map = "" | split: "" %}

{% for doc in all_docs %}
{% for cat in doc.categories %}
{% assign key = cat | downcase %}
{% assign found = false %}
{% for entry in categories_map %}
{% if entry[0] == key %}
{% assign entry = entry[1] | push: doc %}
{% assign categories_map = categories_map | where_exp: "e", "e[0] != key" | push: [key, entry] %}
{% assign found = true %}
{% endif %}
{% endfor %}
{% unless found %}
{% assign categories_map = categories_map | push: [key, [doc]] %}
{% endunless %}
{% endfor %}
{% endfor %}

{% include posts-taxonomy.html taxonomies=categories_map %}
