---
title: Papers
permalink: /papers/
layout: page
subtitle: "arXiv papers"
---

{% assign papers = site.data.papers | sort: "year" | reverse %}


<ul class="list">
  {% for p in papers %}
    <li>
      <div>
        <a href="{{ p.arxiv }}"><strong>{{ p.title }}</strong></a>
        <span class="muted">({{ p.year }})</span>
      </div>
      {% if p.authors %}
        <div class="muted">{{ p.authors }}</div>
      {% endif %}
      {% if p.projects and p.projects.size > 0 %}
        <div class="muted">
          projects:
          {% for pr in p.projects %}
            <a href="/research/{{ pr }}/">{{ pr }}</a>{% unless forloop.last %},{% endunless %}
          {% endfor %}
          {% if p.status %} · {{ p.status }}{% endif %}
        </div>
      {% elsif p.status %}
        <div class="muted">{{ p.status }}</div>
      {% endif %}
    </li>
  {% endfor %}
</ul>
