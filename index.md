---
title: "about"
layout: default
---

{% assign profile = site.static_files | where: "path", "/assets/img/profile.jpg" | first %}

<div class="clearfix" markdown="1">
{% if profile %}
<div class="profile">
  <img src="{{ '/assets/img/profile.jpg' | relative_url }}" alt="Photo of Oliver Wang">
  <div class="profile-caption">NESL, UCLA</div>
</div>
{% endif %}
<h1 class="about-title"><strong>{{ site.first_name }}</strong> {{ site.last_name }}</h1>
<p class="about-subtitle">M.S. student, Electrical Engineering, UCLA · NSF Graduate Research Fellow</p>

I'm a master's student at UCLA, working with Prof. Mani Srivastava in the [Networked and Embedded Systems Lab (NESL)](https://nesl.ee.ucla.edu/). I finished my B.S. in Electrical Engineering at UCLA in June 2026.

My research is about one question: **when should a system trust what it has learned?** Forecasters, robots, and sensing pipelines are all built from past data, and the world they run in keeps changing. I look for cheap ways to tell when a model's predictions or memories have stopped being reliable, and for what the system should do once they have.

**How I got here.** My first project, in high school, was on pruning neural networks to make them smaller. At UCLA I started on the hardware side, calibrating an insertable glucose sensor in Aydogan Ozcan's lab. I spent the summer of 2023 at Cross Labs in Kyoto, getting a language model to turn cocktail recipes into robot commands. At NESL I moved to time series, and found that a simple spectral score can tell you in seconds whether a large forecasting model will beat a small one on your data. That work led to the robotics questions I work on now. A home robot that remembers where your keys are has the same problem as a forecaster when your routine changes: its past data is suddenly wrong, and it may not know it.
</div>

## Interests

<ul class="interests">
  <li>Knowing when to trust a model: reliability signals for forecasting and foundation models</li>
  <li>Memory for robots in homes where people's routines change</li>
  <li>Uncertainty that stays honest after the data shifts</li>
  <li>Detecting real-world events from mixed sensor and text data</li>
</ul>

## News

<table class="news">
  {% for item in site.data.news limit: 6 %}
  <tr><th>{{ item.date }}</th><td>{{ item.text | markdownify | remove: "<p>" | remove: "</p>" }}</td></tr>
  {% endfor %}
</table>

## Selected publications

<ul class="pubs">
  {% assign selected = site.data.publications | where: "selected", true %}
  {% for pub in selected %}{% include publication.html pub=pub %}{% endfor %}
</ul>

<p><a href="{{ '/publications/' | relative_url }}">All publications →</a></p>

{% include social.html %}
