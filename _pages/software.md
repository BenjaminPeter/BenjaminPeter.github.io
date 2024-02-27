---
title: "Peter Lab - Software"
layout: gridlay
excerpt: "Peter Lab Software."
sitemap: false
permalink: /software/
---


# Software



{% assign number_printed = 0 %}
{% for sw in site.data.software %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if sw.highlight == 1 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
 <div class="well">
  <pubtit>{{ sw.title }}</pubtit>
  <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ sw.image }}" class="img-responsive" width="33%" style="float: left" />
  <p>{{ sw.authors }}</p>
  <p><strong><a target="_blank" href="{{ sw.link.paper }}">{{ sw.journal }} ({{sw.year}})</a></strong></p>
  <p><em><a target="_blank" href="{{ sw.link.program }}">Source Code ({{sw.language}})</a></em></p>
  <p>{{ sw.description }}</p>
 </div>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endif %}
{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}

<!--
## Full List of publications

{% for sw in site.data.software %}

  {{ sw.title }} ({{ sw.year }})<br />
  <em>{{ sw.authors }} </em><br /><a target="_blank" href="{{ sw.link.url }}">{{ sw.journal }}</a>

{% endfor %}
-->
