---
title: "projects"
layout: default
subtitle: "What I've worked on, and the question behind each one."
---

{% assign groups = site.data.projects | group_by: "group" %}
{% for group in groups %}
## {{ group.name }}

<div class="projects">
  {% for p in group.items %}
  <article class="project">
    {% if p.image %}<img src="{{ '/assets/img/projects/' | append: p.image | relative_url }}" alt="{{ p.title | escape }}" loading="lazy">{% endif %}
    <div class="project-body">
      <h3 class="project-title">{{ p.title }}</h3>
      <div class="project-meta">{{ p.period }}</div>
      <p class="project-question">{{ p.question }}</p>
      <p class="project-summary">{{ p.summary }}</p>
      {% if p.links %}
      <div class="pub-links">
        {% for link in p.links %}<a class="btn" href="{{ link.url }}">{{ link.label }}</a>{% endfor %}
      </div>
      {% endif %}
    </div>
  </article>
  {% endfor %}
</div>
{% endfor %}
