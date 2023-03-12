---
title: "논문 리뷰를 합시다."
layout: archive
permalink: categories/paper
author_profile: true
sidebar_main: true
---

![paper.png](../../../image/paper.png)


<br><br><br><br>

{% assign posts = site.categories.paper %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}