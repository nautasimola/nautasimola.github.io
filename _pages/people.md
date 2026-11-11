---
layout: page
permalink: /people/
title: People
eyebrow: The team
description: Researchers at DTU Physics and the Max Planck Institute for the Structure and Dynamics of Matter in Hamburg.
wide: true
groups:
  - title: Group leader
    importance: 1
  - title: Postdoctoral researchers
    importance: 2
  - title: PhD students
    importance: 3
---
{%- assign members = site.people | where: "category", "toshow" %}
{%- for g in page.groups %}
{%- assign list = members | where: "importance", g.importance | sort: "title" %}
{%- if list.size > 0 %}
<h2 class="group-title">{{ g.title }}</h2>
<div class="people-grid">
  {%- for person in list %}
    {% include person-card.html person=person %}
  {%- endfor %}
</div>
{%- endif %}
{%- endfor %}

{%- assign alumni = site.people | where: "category", "alumni" | sort: "title" %}
{%- if alumni.size > 0 %}
<h2 class="group-title">Alumni</h2>
<ul class="alumni-list">
  {%- for a in alumni %}
  <li>{% if a.redirect != blank %}<a href="{{ a.redirect }}"><strong>{{ a.title }}</strong></a>{% else %}<strong>{{ a.title }}</strong>{% endif %}<span>{{ a.description }}</span></li>
  {%- endfor %}
</ul>
{%- endif %}
