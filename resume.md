---
layout: page
title: Resume
permalink: /resume/
description: My professional background, experience, and skills.
---

<div class="resume-header">
  <p class="resume-summary">
    <!-- A 2–3 sentence summary that's worth reading. Lead with what you
         do and what you're good at, not "results-driven professional". -->
    [Your name] is a [role] specializing in [domain]. Currently
    [current focus at current company]. Previously [one notable
    earlier chapter].
  </p>

  <p class="resume-contact">
    <a href="mailto:{{ site.author.email }}">{{ site.author.email }}</a> ·
    <a href="https://github.com/{{ site.social.github }}">GitHub</a> ·
    <a href="https://linkedin.com/in/{{ site.social.linkedin }}">LinkedIn</a> ·
    <a href="{{ '/assets/resume.pdf' | relative_url }}">Download PDF</a>
  </p>
</div>

## Experience

{% comment %}
  Sort experience by start date, newest first. Liquid sorts strings
  lexicographically, which works correctly for YYYY-MM format.
{% endcomment %}
{% assign jobs = site.data.experience | sort: "start" | reverse %}

{% for job in jobs %}
<section class="resume-job">

  <header class="resume-job__header">
    <h3 class="resume-job__title">
      {{ job.role }} ·
      {% if job.company_url %}
        <a href="{{ job.company_url }}">{{ job.company }}</a>
      {% else %}
        {{ job.company }}
      {% endif %}
    </h3>
    <p class="resume-job__meta">
      {% assign start_parts = job.start | split: "-" %}
      {{ start_parts[1] }}/{{ start_parts[0] }} –
      {% if job.end %}
        {% assign end_parts = job.end | split: "-" %}
        {{ end_parts[1] }}/{{ end_parts[0] }}
      {% else %}
        Present
      {% endif %}
      {% if job.location %} · {{ job.location }}{% endif %}
    </p>
  </header>

  <p class="resume-job__summary">{{ job.summary }}</p>

  {% if job.highlights %}
  <ul class="resume-job__highlights">
    {% for highlight in job.highlights %}
      <li>{{ highlight }}</li>
    {% endfor %}
  </ul>
  {% endif %}

  {% if job.stack %}
  <p class="resume-job__stack">
    <strong>Stack:</strong> {{ job.stack | join: " · " }}
  </p>
  {% endif %}

</section>
{% endfor %}

## Skills

<div class="resume-skills">
{% for group in site.data.skills %}
  <div class="resume-skills__group">
    <h4>{{ group.category }}</h4>
    <ul>
      {% for item in group.items %}
        <li>{{ item }}</li>
      {% endfor %}
    </ul>
  </div>
{% endfor %}
</div>

## Education

<!-- Education is usually short enough that hand-writing it as Markdown
     is fine. Promote it to _data/ if you want to add coursework,
     activities, or multiple degrees with detail. -->

**[Degree], [Field]** — [University Name], [Year]
[One line on honors, thesis, or relevant focus, if worth mentioning.]

## Speaking & Writing

<!-- Optional. Remove if you don't have these yet. -->

- **[Talk title]** — [Conference], [Year]. [One-line description, with link.]
- **[Article title]** — [Publication], [Year]. [Link.]

---

*Looking for a printable version? [Download the PDF]({{ '/assets/resume.pdf' | relative_url }}).*
