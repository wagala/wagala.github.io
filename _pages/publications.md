---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
You can also find my articles on my Google Scholar profile.
{% endif %}

{% include base_path %}

{% assign methodology_publications = site.publications
  | where: "category", "methodology"
  | sort: "date"
  | reverse %}

{% assign application_publications = site.publications
  | where: "category", "applications"
  | sort: "date"
  | reverse %}

{% assign method_size = methodology_publications | size %}

## Statistical Methodology

{% for post in methodology_publications %}
{{ forloop.index }}. {% include archive-single.html %}
{% endfor %}

## Applications

{% for post in application_publications %}
{% assign pub_num = forloop.index | plus: method_size %}
{{ pub_num }}. {% include archive-single.html %}
{% endfor %}