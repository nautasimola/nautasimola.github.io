---
layout: page
permalink: /projects/
title: Research
eyebrow: What we work on
description: Our research combines quantum electrodynamics with first-principles materials theory to understand and design matter driven by light.
wide: true
---
{%- assign projects = site.projects | where: "category", "work" | sort: "importance" %}
<div class="project-grid">
  {%- for pr in projects %}
    {% include project-card.html project=pr index=forloop.index %}
  {%- endfor %}
</div>
