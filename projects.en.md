---
layout: page
title: My Projects
permalink: /projects.en.html
lang: en
---

<!-- # 我的项目 -->
 Show my Projects 

{% assign en_projects = site.projects | where: "lang", "en" | sort: 'date' | reverse %}
{% for project in en_projects %}
  <div style="margin-bottom: 20px;">  
     <h3><a href="{{ project.url }}">{{ project.title }}</a></h3>
     <p>{{ project.excerpt }}</p>
     <p><a href="{{ project.url }}">view details →</a></p>  
  </div>
{% endfor %}