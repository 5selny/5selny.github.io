---
title: "blog"
layout: archive
permalink: categories/blog
author_profile: true
sidebar_main: true
nav: "docs"
---


{% assign posts = site.categories.blog %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}
