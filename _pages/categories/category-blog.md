---
title: "블로그(Blog)"
layout: archive
permalink: /categories/blog
author_profile: true
category_nav: true
---
{% assign posts = site.categories.blog %}
{% for post in posts %} {% include category-single.html type=page.entries_layout %} {% endfor %}