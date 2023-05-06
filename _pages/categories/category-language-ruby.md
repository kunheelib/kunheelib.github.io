---
title: "루비(Ruby)"
layout: archive
permalink: /categories/ruby
author_profile: true
category_nav: true
---
{% assign posts = site.categories['ruby'] %}
{% for post in posts %} {% include category-single.html type=page.entries_layout %} {% endfor %}