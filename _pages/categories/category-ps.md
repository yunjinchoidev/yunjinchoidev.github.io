---
title: "aitech-ps"
layout: archive
permalink: categories/ps
author_profile: true
sidebar_main: true
---


<p align="center">
<img src="../../../image/algo.png" 
width="400" height="400"/>
</p>

<div class="container">
</div>

<style>
.container {
  display: flex;
  align-items: center;
  height: 100px;
}
</style>


{% assign posts = site.categories.ps %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}