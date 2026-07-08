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
</li>
{% endfor %}
</ul>
</div>
