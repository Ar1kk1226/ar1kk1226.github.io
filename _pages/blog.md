---
layout: page
title: 博客
---
# 我的博客
这里会显示所有文章列表：

{% for post in site.posts %}
  <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
  <p>{{ post.date | date: "%Y-%m-%d" }}</p>
{% endfor %}