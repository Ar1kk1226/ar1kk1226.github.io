---
layout: page
title: My Projects
permalink: /projects.en.html
lang: en
---

<!-- # 我的项目 -->
 Show my Projects 

{% for project in site.projects %}
  {% if project.lang == 'en' %}
  <div style="margin-bottom: 20px;">  
     <h3><a href="{{ project.url }}">{{ project.title }}</a></h3>
       <p>{{ project.excerpt }}</p>
     <p><a href="{{ project.url }}">view details →</a></p>  
   </div>
  {% endif %}
{% endfor %}