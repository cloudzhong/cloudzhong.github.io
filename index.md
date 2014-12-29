---
layout: page
title: Cloud Zhong的记录
tagline: Supporting tagline
---

## Posts List
尝试使用github + Jekyll Bootstrap写点东西

博客列表：

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

## To-Do
如何更新Jekyll Bootstrap ?



