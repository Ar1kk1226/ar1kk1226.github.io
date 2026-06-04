---
layout: page
title: 我的项目
permalink: /projects/
---

<!-- # 我的项目 -->
这里展示我做过的开源项目 / 作品

{% for project in site.projects %}
<div style="margin-bottom: 20px;">
  <h3><a href="{{ project.url }}">{{ project.title }}</a></h3>
  <p>{{ project.excerpt }}</p>
  <p><a href="{{ project.url }}">查看详情 →</a></p>
</div>
{% endfor %}
