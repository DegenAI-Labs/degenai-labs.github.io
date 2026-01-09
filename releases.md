---
title: Releases
permalink: /releases/
layout: page
subtitle: "Code repos, datasets, benchmarks, tools, and model drops — versioned and citable."
---

{% assign rels = site.releases | sort: "date" | reverse %}

<ul class="list">
  {% for r in rels %}
    <li>
      <div>
        <a href="{{ r.url }}"><strong>{{ r.title }}</strong></a>
        {% if r.artifact_type %}<span class="pill">{{ r.artifact_type }}</span>{% endif %}
        {% if r.version %}<span class="muted">v{{ r.version }}</span>{% endif %}
      </div>
      <div class="muted">
        {{ r.date | date: "%Y-%m-%d" }}
        {% if r.project %} · project: <a href="/research/{{ r.project }}/">{{ r.project }}</a>{% endif %}
      </div>
    </li>
  {% endfor %}
</ul>

<!-- <p class="muted">
Releases are first-class artifacts (separate from blog posts). Use them for anything you want people to cite, download, or reproduce.
</p> -->
