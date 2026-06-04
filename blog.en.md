---
layout: page
title: My Blog
permalink: /blog.en.html
lang: en
---

<!--   我的博客    -->
Record my study & daily life.

{% for blog in site.posts %}
{% if blog.lang == 'en' %}
<div style="margin: 25px 0; border-bottom:1px solid #eee; padding-bottom:15px;">
 <h3>  
   <a href="{{ blog.url }}" style="text-decoration:none; color:#2b6cb0;">
   {{ blog.title }}
   </a>    
 </h3>
  <small style="color:#888;">📅 {{ blog.date | date: "%B %d, %Y" }}</small>
 <p style="color:#555; margin-top:8px;">
   {{ blog.excerpt | strip_html | truncate: 120 }}
 </p>
</div>
{% endif %}
{% endfor %}