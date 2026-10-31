---
title: "about"
layout: default
---

{% assign profile = site.static_files | where: "path", "/assets/img/profile.jpg" | first %}

<div class="clearfix" markdown="1">
{% if profile %}
<div class="profile">
  <img src="{{ '/assets/img/profile.jpg' | relative_url }}" alt="Photo of Oliver Wang">
  <div class="profile-caption"></div>
</div>
{% endif %}
<h1 class="about-title"><strong>{{ site.first_name }}</strong> {{ site.last_name }}</h1>
<p class="about-subtitle">M.S. student, Electrical Engineering, UCLA · NSF Graduate Research Fellow</p>

I'm a master's student at UCLA, working with Prof. Mani Srivastava in the [Networked and Embedded Systems Lab (NESL)](https://nesl.ee.ucla.edu/) and with Prof. Abeer Alwan in the Speech Processing and Auditory Perception Lab (SPAPL). I finished my B.S. in Electrical Engineering at UCLA in June 2026.

I'm interested in robots and agents that keep getting better over long-term deployment. My current work examines how home robots should update their memories as household routines change, and whether model confidence helps identify incorrect predictions. I'm now testing these ideas on a Unitree Go2 quadruped, where the real world brings failures that never showed up in simulation. I also lead the research direction of a project with Sandia National Laboratories on detecting urban events like wildfires and traffic accidents from cameras, sensors, and social media. Meanwhile, I've also enjoyed working with time-series, such as identifying whether a given time-series foundation model is suitable for a dataset.

## Interests

<ul class="interests">
  <li>Memory that revises its beliefs as environments and human routines change</li>
  <li>Uncertainty that stays meaningful under distribution shift</li>
  <li>Agents that diagnose and learn from their own failures</li>
  <li>Knowing when to trust a model (reliability signals for foundation models)</li>
</ul>

## Selected publications

<ul class="pubs">
  {% assign selected = site.data.publications | where: "selected", true %}
  {% for pub in selected %}{% include publication.html pub=pub %}{% endfor %}
</ul>

<p><a href="{{ '/publications/' | relative_url }}">All publications →</a></p>

## News

<table class="news">
  {% for item in site.data.news limit: 6 %}
  <tr><th>{{ item.date }}</th><td>{{ item.text | markdownify | remove: "<p>" | remove: "</p>" }}</td></tr>
  {% endfor %}
</table>

{% include social.html %}
