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
<a href="https://www.notion.so/yunjinchoidev/3-9feca316a9054f5a9f2a06b0a3fb9981?pvs=4" style="font-size:40px; color:red; text-align: center;"> 노션 링크 바로가기</a>
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