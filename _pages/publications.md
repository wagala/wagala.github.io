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

## Statistical Methodology

{% for post in methodology_publications %}
  {% include archive-single.html pub_index=forloop.index %}
{% endfor %}

## Applications

{% assign offset = methodology_publications.size %}
{% for post in application_publications %}
  {% assign current_index = forloop.index | plus: offset %}
  {% include archive-single.html pub_index=current_index %}
{% endfor %}