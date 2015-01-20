---
layout: page
title: 千里之行，始于足下
tagline: 前事不忘，后事之师
---

尝试使用github + Jekyll Bootstrap写点东西

##博客列表：

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date: "%Y年%m月%d日" }}</span>
		<h4><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></h4>
		<div>
		{{ post.excerpt | remove: '<p>' | remove: '</p>' }}
		<span><a href="{{ BASE_PATH }}{{ post.url }}">阅读全文 &raquo;</a></span>
		</div>
		<hr>
	</li>
  {% endfor %}
</ul>

