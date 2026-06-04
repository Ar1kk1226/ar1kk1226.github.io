---
layout: page
title: 我的博客
permalink: /blog.zh.html
lang: zh
---

<!--   我的博客    -->
这里记录了我的日常学习、生活和感悟

{% for blog in site.posts %}
{% if blog.lang == 'zh' %}
<div style="margin: 25px 0; border-bottom:1px solid #eee; padding-bottom:15px;">
 <h3>  
   <a href="{{ blog.url }}" style="text-decoration:none; color:#2b6cb0;">
   {{ blog.title }}
   </a>    
 </h3>
  <small style="color:#888;">📅 {{ blog.date | date: "%Y年%m月%d日" }}</small>
 <p style="color:#555; margin-top:8px;">
   {{ blog.excerpt | strip_html | truncate: 120 }}
 </p>
</div>
{% endif %}
{% endfor %}
