---
title: "aitech-주간 회고"
layout: archive
permalink: categories/aitech_weekly
author_profile: true
sidebar_main: true
toc: true
toc_sticky: true
toc_label: "목차"
---

<br>

![image](../../../image/aitech.png)


{% assign posts = site.categories.aitech_weekly %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}