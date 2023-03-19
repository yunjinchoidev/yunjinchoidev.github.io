---
title: "논문 리뷰를 합시다."
layout: archive
permalink: categories/paper
author_profile: true
sidebar_main: true
---

<p align="center">
<img src="../../../image/paper.png" 
width="400" height="400"/>
</p>

<br><br><br><br>

{% assign posts = site.categories.paper %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}