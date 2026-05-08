---
layout: home
title: Home
permalink: /
---

<section class="home-hero">

  <h1 class="home-hero__name">{{ site.author.name }}</h1>

  <p class="home-hero__bio">
    <!-- One sentence. Resist the urge to add a second.
         Good: "I build data infrastructure at Example Corp and write
         occasionally about distributed systems."
         Less good: "Passionate, results-driven engineer with a love
         for clean code and challenging problems." -->
    {{ site.author.bio }}
  </p>

  <nav class="home-hero__links" aria-label="Primary">
    <a href="{{ '/projects/' | relative_url }}">Projects</a>
    <a href="{{ '/about/' | relative_url }}">About</a>
    <a href="{{ '/resume/' | relative_url }}">Resume</a>
  </nav>

  <nav class="home-hero__social" aria-label="Elsewhere">
    <a href="mailto:{{ site.author.email }}">Email</a>
    <a href="https://github.com/{{ site.social.github }}" rel="me">GitHub</a>
    <a href="https://linkedin.com/in/{{ site.social.linkedin }}" rel="me">LinkedIn</a>
    {% if site.social.mastodon != "" %}
      <a href="{{ site.social.mastodon }}" rel="me">Mastodon</a>
    {% endif %}
  </nav>

</section>
