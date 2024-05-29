---
title: "Home"
layout: textlay
excerpt: "Peter Lab at the University of Rochester"
sitemap: false
permalink: /allnews.html
---

# News
{% for article in site.data.news limit:5 %}
<small><i>{{ article.date }}</i></small>

<div class="col-sm-12">
### [{{article.headline}}]({{article.link}})
{% if article contains "image" %}
<img src="{{site.url}}/images/{{article.image}}" width="50%" 
style="float:left; margin-right:20px"/>
{% endif %}
{{ article.text }}
</div>

{% endfor %}

