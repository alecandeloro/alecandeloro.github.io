---
layout: default
title: Research
---

## Publications

*A complete publication list is available on
[Google Scholar](https://scholar.google.com/).*

{% assign publications = site.data.publications | sort: "year" | reverse %}

<div class="publication-list">

{% assign current_year = "" %}

{% for paper in publications %}

{% if paper.year != current_year %}

{% assign current_year = paper.year %}

<h2 class="publication-year">{{ paper.year }}</h2>

{% endif %}

<div class="publication-item">

<div class="publication-title">
<strong>{{ paper.title }}</strong>
</div>

<div class="publication-authors">
{{ paper.authors }}
</div>

<div class="publication-journal">
<i>{{ paper.journal }}</i> {{ paper.volume }}
</div>

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
