---
layout: page
permalink: /news/
title: News
eyebrow: Updates
description: Grants, events, new members and other updates from the group.
wide: true
---
{%- assign news = site.news | sort: "date" | reverse %}
<div class="news-list">
  {%- for item in news %}
    {% include news-item.html item=item %}
  {%- endfor %}
</div>
