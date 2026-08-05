---
layout: default
title: Research
---

## Publications

*A complete publication list is available on
[Google Scholar](https://scholar.google.com/).*

{% assign publications = site.data.publications | sort: "year" | reverse %}

{% for paper in publications %}

<div class="publication-card">

<h3>
{{ paper.title }}
</h3>
<p>
{{ paper.authors }}
</p>

<p>
<i>{{ paper.journal }}</i>
<strong>{{ paper.volume }}</strong>
({{ paper.year }})
</p>

<div class="publication-links">

{% if paper.doi %}
<a href="{{ paper.doi }}">🔗 DOI</a>
{% endif %}

{% if paper.arxiv %}
<a href="{{ paper.arxiv }}">📄 arXiv</a>
{% endif %}

</div>

</div>

{% endfor %}
