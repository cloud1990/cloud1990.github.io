---
title: "Members"
layout: gridlay
sitemap: false
permalink: /members/
---

<!--- Jump to [staff](#staff), [master and bachelor students](#master-and-bachelor-students), [alumni](#alumni), [administrative support](#administrative-support), [lab visitors](#lab-visitors). -->

### 教师 Faculty

{% for member in site.data.pi %}

<div class="faculty-row">
  <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="member-photo member-photo-faculty" alt="{{ member.name }}" />
  <h4>{{ member.name }}</h4>
  <i>{{ member.info }}</i><br>
  {% if member.website %}<a href="{{ member.website }}" target="_blank"><i class="fa fa-home fa-2x"></i></a> {% endif %}{% if member.email %}<a href="mailto:{{ member.email }}" target="_blank"><i class="fa fa-envelope-square fa-2x"></i></a> {% endif %}{% if member.scholar %}<a href="{{ member.scholar }}" target="_blank"><i class="ai ai-google-scholar-square ai-2x"></i></a> {% endif %}{% if member.github %}<a href="{{ member.github }}" target="_blank"><i class="fa fa-github-square fa-2x"></i></a> {% endif %}{% if member.researchgate %}<a href="{{ member.researchgate }}" target="_blank"><i class="ai ai-researchgate-square ai-2x"></i></a> {% endif %}{% if member.cv %}<a href="{{ member.cv }}" target="_blank"><i class="ai ai-cv-square ai-2x"></i></a> {% endif %}
  <ul class="member-educ-list">
  {% for i in (1..member.number_educ) %}
    {% assign edu_key = "education" | append: i %}
    <li>{{ member[edu_key] }}</li>
  {% endfor %}
  </ul>
</div>

{% endfor %}

<hr class="section-divider">

## 在读研究生 Current Graduate Student
{% assign number_printed = 0 %}
{% for member in site.data.team_members %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix member-card-student">
  <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="member-photo member-photo-student" alt="{{ member.name }}" />
  <h4>{{ member.name }}</h4>
  <i>{{ member.info }}<br></i>
  {% if member.website %}<a href="{{ member.website }}" target="_blank"><i class="fa fa-home fa-2x"></i></a> {% endif %}  {% if member.email %}<a href="mailto:{{ member.email }}" target="_blank"><i class="fa fa-envelope-square fa-2x"></i></a> {% endif %}  {% if member.scholar %} <a href="{{ member.scholar }}" target="_blank"><i class="ai ai-google-scholar-square ai-2x"></i></a> {% endif %}  {% if member.cv %} <a href="{{ member.cv }}" target="_blank"><i class="ai ai-cv-square ai-2x"></i></a> {% endif %}  {% if member.github %} <a href="{{ member.github }}" target="_blank"><i class="fa fa-github-square fa-2x"></i></a> {% endif %}  {% if member.researchgate %} <a href="{{ member.researchgate }}" target="_blank"><i class="ai ai-researchgate-square ai-2x"></i></a> {% endif %}
  <ul class="member-educ-list">
  {% for i in (1..member.number_educ) %}
    {% assign edu_key = "education" | append: i %}
    <li>{{ member[edu_key] }}</li>
  {% endfor %}
  </ul>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}

<hr class="section-divider">

## 已毕业研究生 Group Alumni

{% for member in site.data.alumni_members %}

<div class="alumni-row">
  <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="alumni-photo" alt="{{ member.name }}" />
  <span class="alumni-info">
    <span class="alumni-name"><strong>{{ member.name }}</strong></span><span class="alumni-meta"> ({{ member.duration }})</span>
    <span class="alumni-bio">{{ member.info }} </span>
  </span>
</div>

{% endfor %}

<hr class="section-divider">

## 团队合影 Group Photos
{% for photo in site.data.group_photos %}
<div>
  <p style="text-align: center; margin-bottom: 2px;">{{ photo.caption }}</p>
  <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ photo.filename }}" alt="{{ photo.caption }}" class="img-fluid" style="display: block; margin: 0 auto; border-radius: 5%; max-width: 60%; height: auto;" />
</div>
<br>
{% endfor %}