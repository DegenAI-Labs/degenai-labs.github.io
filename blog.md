---
title: Blog
permalink: /blog/
layout: page
subtitle: "Research notes, updates, and announcements."
---

{% assign posts = site.posts %}

<ul class="list">
  {% for post in posts %}
    <li>
      <div>
        <a href="{{ post.url }}"><strong>{{ post.title }}</strong></a>
      </div>
      <div class="muted">
        {{ post.date | date: "%Y-%m-%d" }}
        {% if post.tags and post.tags.size > 0 %}
          ·
          {% for t in post.tags %}
            <span class="tag">{{ t }}</span>
          {% endfor %}
        {% endif %}
      </div>
    </li>
  {% endfor %}
</ul>
