---
layout: page
permalink: /publications/
title: Publications
eyebrow: Output
description: Peer-reviewed articles and preprints in reverse chronological order. See Google Scholar for citation metrics.
wide: true
years: [2026, 2025, 2024, 2023, 2022, 2021, 2020, 2019, 2018, 2017, 2016, 2015, 2014]
---
<p class="pub-links">
  <a class="btn btn--ghost btn--sm" href="{{ site.socials.scholar }}">Google Scholar</a>
  <a class="btn btn--ghost btn--sm" href="{{ site.socials.orcid }}">ORCID</a>
</p>
<div class="publications">
  <h2 class="year">Preprints</h2>
  {% bibliography -f papers -q @misc %}

  <h2 class="pub-section">Journal articles</h2>
{%- for y in page.years %}
  {%- capture block %}{% bibliography -f papers -q @article[year={{y}}] %}{% endcapture %}
  {%- if block contains "<li" %}
  <h3 class="year">{{ y }}</h3>
  {{ block }}
  {%- endif %}
{%- endfor %}
</div>
