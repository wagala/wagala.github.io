---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{ author.googlescholar }}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% assign all_publications = site.publications | sort: "date" | reverse %}
{% assign methodology_publications = all_publications | where: "category", "methodology" %}
{% assign application_publications = all_publications | where: "category", "applications" %}

<div class="publications-list">

## Statistical Methodology

<div class="publication-section">
{% for post in methodology_publications %}
  {% include archive-single.html %}
{% endfor %}
</div>

## Applications

<div class="publication-section">
{% for post in application_publications %}
  {% include archive-single.html %}
{% endfor %}
</div>

</div>