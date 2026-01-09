---
title: Research
permalink: /research/
layout: page
subtitle: "Ongoing and future work."
---

{% assign projects = site.projects | sort: "title" %}

<ul class="list">
  {% for p in projects %}
    <li>
      <a href="{{ p.url }}"><strong>{{ p.title }}</strong></a>
      {% if p.status %}<span class="pill">{{ p.status }}</span>{% endif %}
      {% if p.excerpt and p.excerpt != "" %}
        <div class="muted">{{ p.excerpt | strip_html | truncate: 140 }}</div>
      {% endif %}
    </li>
  {% endfor %}
</ul>

<!-- <p class="muted">
Projects are intended to be stable references; interim updates go to the blog and concrete outputs go to releases.
</p> -->
