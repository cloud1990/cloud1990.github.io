---
title: "Projects"
layout: gridlay
sitemap: false
permalink: /projects/
---

### 项目介绍 Projects

课题组承担国家自然科学基金、国家重点研发计划子课题、省部级重点研发项目及企业横向课题等。按在研与已结题分列如下。

The group undertakes projects funded by the National Natural Science Foundation of China, sub-projects of the National Key R&D Program, provincial and ministerial key R&D programs, and industry-sponsored research. They are listed below by status.

<hr class="section-divider">

## 在研项目 Ongoing Projects

<div class="jumbotron">
<ul class="project-list">
{% for grant in site.data.grants %}
{% if grant.status == "ongoing" %}
 <li> {{ grant.name }}{% if grant.name_en %}<br><span class="grant-en">{{ grant.name_en }}</span>{% endif %} </li>
{% endif %}
{% endfor %}
</ul>
</div>

<hr class="section-divider">

## 已结题项目 Completed Projects

<div class="jumbotron">
<ul class="project-list">
{% for grant in site.data.grants %}
{% if grant.status != "ongoing" %}
 <li> {{ grant.name }}{% if grant.name_en %}<br><span class="grant-en">{{ grant.name_en }}</span>{% endif %} </li>
{% endif %}
{% endfor %}
</ul>
</div>
