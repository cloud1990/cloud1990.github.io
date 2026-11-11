---
title: "News"
layout: textlay
sitemap: false
permalink: /allnews.html
---

## News

<div class="jumbotron">
<ul class="news-list">
{% for article in site.data.news %}
<li>
<b>{{ article.date }}</b>
{{ article.headline }}
{% if article.headline_en %}<div class="news-en">{{ article.headline_en }}</div>{% endif %}
</li>
{% endfor %}
</ul>
</div>
