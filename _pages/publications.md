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

## Statistical Methodology

{% assign methodology_publications = site.publications
  | where: "category", "methodology"
  | sort: "date"
  | reverse %}

{% for post in methodology_publications %}
  {% include archive-single.html %}
{% endfor %}

## Applications

{% assign application_publications = site.publications
  | where: "category", "applications"
  | sort: "date"
  | reverse %}

{% for post in application_publications %}
  {% include archive-single.html %}
{% endfor %}