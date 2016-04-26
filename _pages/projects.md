---
title: "Projects"
layout: single
excerpt: "Some side-projects I have been doing"
sitemap: true
permalink: /projects/
---

{% for page in site.pages %}
{% if page.categories contains 'project' %}
[{{page.title}}]{{{page.permalink}}}
------------------------------------
      
{{page.excerpt}}
{% endif %}
{% endfor %}