---
layout: page
title: 我的项目
permalink: /projects.zh.html
lang: zh
---

<!-- # 我的项目 -->
这里展示我做过的开源项目 / 作品

{% assign en_projects = site.projects | where: "lang", "zh" | sort: 'date' | reverse %}
{% for project in en_projects %}
  <div style="margin-bottom: 20px;">  
     <h3><a href="{{ project.url }}">{{ project.title }}</a></h3>
     <p>{{ project.excerpt }}</p>
     <p><a href="{{ project.url }}">view details →</a></p>  
  </div>
{% endfor %}