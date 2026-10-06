---
title: "publications"
layout: default
subtitle: "Workshop papers, journal articles, and preprints. Newest first."
---

{% assign by_year = site.data.publications | group_by: "year" %}
{% for group in by_year %}
<h2 class="year">{{ group.name }}</h2>
<ul class="pubs">
  {% for pub in group.items %}{% include publication.html pub=pub %}{% endfor %}
</ul>
{% endfor %}
