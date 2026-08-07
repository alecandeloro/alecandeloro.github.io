---
layout: default
title: Research
---

<div class="publications-header">
  <div>
    <h2 class="publications-title">Publications</h2>
    <p class="publications-subtitle">
      Selected publications and preprints.
    </p>
  </div>

  <a class="scholar-button"
     href="https://scholar.google.com/"
     target="_blank"
     rel="noopener">
    Google Scholar ↗
  </a>
</div>

{% assign publications = site.data.publications | sort: "year" | reverse %}

<div class="publication-list">

{% for paper in publications %}

<article class="publication-card">

  <div class="publication-main">

    <div class="publication-top">

      <h3 class="publication-title">
        {{ paper.title }}
      </h3>

      <span class="publication-year">
        {{ paper.year }}
      </span>

    </div>

    <div class="publication-journal">
      <span class="publication-icon">▮</span>
      <span>{{ paper.journal }}</span>
      {% if paper.volume %}
        <span class="publication-volume">{{ paper.volume }}</span>
      {% endif %}
    </div>

    <div class="publication-authors">
      <span class="publication-icon">♟</span>
      <span>
        <strong>Authors:</strong> {{ paper.authors }}
      </span>
    </div>

    <div class="publication-actions">

      {% if paper.doi %}
        <a href="{{ paper.doi }}"
           target="_blank"
           rel="noopener"
           class="publication-link">
          VIEW PUBLICATION ↗
        </a>
      {% elsif paper.arxiv %}
        <a href="{{ paper.arxiv }}"
           target="_blank"
           rel="noopener"
           class="publication-link">
          VIEW PUBLICATION ↗
        </a>
      {% endif %}

      {% if paper.abstract %}
        <details class="abstract-details">
          <summary>SHOW ABSTRACT <span>⌄</span></summary>
          <div class="abstract-content">
            {{ paper.abstract }}
          </div>
        </details>
      {% endif %}

    </div>

  </div>

</article>

{% endfor %}

</div>
