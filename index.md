---
layout: page
title: 千里之行，始于足下
tagline: Supporting tagline
---

尝试使用github + Jekyll Bootstrap写点东西

##博客列表：

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

