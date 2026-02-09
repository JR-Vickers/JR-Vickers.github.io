---
layout: page
title: Essays
permalink: /essays/
---

# Essays

<hr class="break">

<div class="essay-list">
{% assign sorted_essays = site.essays | sort: 'date' | reverse %}
{% for essay in sorted_essays %}
<article>
<h2><a href="{{ essay.url | relative_url }}">{{ essay.title }}</a></h2>
<time datetime="{{ essay.date | date: '%Y-%m-%d' }}">{{ essay.date | date: "%B %d, %Y" }}</time>
{% if essay.description %}
<p>{{ essay.description }}</p>
{% endif %}
</article>
<hr class="break">
{% endfor %}
</div>
