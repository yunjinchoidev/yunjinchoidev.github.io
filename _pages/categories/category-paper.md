---
title: "논문 리뷰를 합시다."
layout: archive
permalink: categories/paper
author_profile: true
sidebar_main: true
---

<img src="../../../image/chatbot/chatbot_lachesis.png" width="400" height="400" />

<br><br><br><br>

{% assign posts = site.categories.paper %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}