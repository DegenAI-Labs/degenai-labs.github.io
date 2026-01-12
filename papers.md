---
title: Papers
permalink: /papers/
layout: page
subtitle: "arXiv papers"
---

{% assign papers = site.data.papers | sort: "date" | reverse %}

<ul class="list">
  {% for p in papers %}
    <li>
      <div class="paper-title">
        <a href="{{ p.arxiv }}"><strong>{{ p.title }}</strong></a>
      </div>

      {% if p.abstract %}
        <div class="paper-abstract">
            <p class="paper-abstract-text">{{ p.abstract }}</p>
        </div>
      {% endif %}

    {% if p.authors %}
        <div class="paper-authors muted small">
          {{ p.authors }}
        </div>
      {% endif %}

    <div class="paper-meta muted">
        {% if p.date %}
        {{ p.date | date: "%B %e, %Y" }}
        {% elsif p.year %}
        {{ p.year }}
        {% endif %}

    {% if p.projects and p.projects.size > 0 %}
        · projects:
        {% for pr in p.projects %}
            <a href="/research/{{ pr }}/">{{ pr }}</a>{% unless forloop.last %},{% endunless %}
        {% endfor %}
        {% endif %}
    </div>

      <div class="paper-links">
        {% if p.arxiv %}<a href="{{ p.arxiv }}">arXiv</a>{% endif %}
        {% if p.pdf %} · <a href="{{ p.pdf }}">PDF</a>{% endif %}
      </div>
    </li>
  {% endfor %}
</ul>
