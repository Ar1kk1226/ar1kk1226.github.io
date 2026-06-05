---
layout: page
title: 主页
permalink: /index.zh.html
lang: zh
---

<style>
/* 主页美化样式 */
.hero {
  text-align: center;
  margin-bottom: 40px;
}
.avatar {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  margin: 0 auto;
  background: #f0f0f0;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 40px;
  color: #666;
}
.bio {
  font-size: 16px;
  color: #555;
  max-width: 700px;
  margin: 20px auto;
  line-height: 1.7;
}
.section-title {
  font-size: 22px;
  margin: 40px 0 20px;
  text-align: center;
  color: #333;
}
/* 技能标签 */
.skills {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 10px;
  margin-bottom: 40px;
}
.skill-tag {
  background: #eef5ff;
  color: #2b6cb0;
  padding: 6px 14px;
  border-radius: 20px;
  font-size: 14px;
}
/* 项目卡片 */
.project-cards {
  display: grid;
  grid-template-columns: repeat(auto-fill(), minmax(280px, 1fr));
  gap: 20px;
  margin-bottom: 40px;
}
.project-card {
  border: 1px solid #eee;
  border-radius: 10px;
  padding: 20px;
  transition: 0.3s;
}
.project-card:hover {
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
}
.project-card h3 {
  margin-top: 0;
  font-size: 18px;
}
.project-card p {
  color: #666;
  font-size: 14px;
}
</style>

<!-- 个人简介 -->
<div class="hero">
  <div class="avatar">
   <img src="/images/my.jpg" alt="我的头像" style="width:120px; height:120px; border-radius:50%;" />
  </div>
  <h1>你好，我是王怡瑞</h1>
  <div class="bio">
    热爱旅游、打篮球、开源、新技术分享。 <br>
    专注于数据分析、各类建模、AI应用开发。<br>
    在学习的同时，喜欢解决生活中遇到的问题，打造简洁实用的作品。
  </div>
</div>

<!-- 技能 -->
<h2 class="section-title">我的技能</h2>
<div class="skills">
  <div class="skill-tag">HTML</div>
  <div class="skill-tag">Python</div>
  <div class="skill-tag">Git</div>
  <div class="skill-tag">Jekyll</div>
  <div class="skill-tag">GitHub Pages</div>
  <div class="skill-tag">Markdown</div>
</div>

<!-- 项目预览 -->
<h2 class="section-title">我的精选项目</h2>
<div class="project-cards">
  {% assign matched_projects = site.projects | where: "lang", page.lang %}
  {% for project in matched_projects limit:3 %}
  <div class="project-card">
    <h3><a href="{{ project.url }}">{{ project.title }}</a></h3>
    <p>{{ project.content | strip_html | truncate: 80 }}</p>
  </div>
  {% endfor %}
</div>


<div style="text-align:center; margin-top:20px;">
{% if page.lang == 'zh' %}
  <a href="/projects.zh.html" style="display:inline-block; padding:10px 20px; background:#2b6cb0; color:white; border-radius:6px; text-decoration:none;">查看全部项目</a>
{% else %}
  <a href="/projects.en.html" style="display:inline-block; padding:10px 20px; background:#2b6cb0; color:white; border-radius:6px; text-decoration:none;">View All Projects</a>
{% endif %}
</div>