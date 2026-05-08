---
layout: page
title: Projects
permalink: /projects/
description: A selection of things I've built, written, or contributed to.
---

{% comment %}
  Sort projects by year (newest first), then render each as a card.
  Featured projects appear in their own section at the top.
{% endcomment %}

{% assign sorted = site.data.projects | sort: "year" | reverse %}
{% assign featured = sorted | where: "featured", true %}
{% assign rest = sorted | where_exp: "p", "p.featured != true" %}

{% if featured.size > 0 %}
## Featured

<div class="project-grid">
  {% for project in featured %}
    {% include project-card.html project=project %}
  {% endfor %}
</div>
{% endif %}

## All projects

<div class="project-grid">
  {% for project in rest %}
    {% include project-card.html project=project %}
  {% endfor %}
</div>
