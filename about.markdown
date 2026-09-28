---
layout: page
title: about
permalink: /about/
---
{% assign current_year = 'now' | date: '%Y' | plus: 0 %}
{% assign start_year = 2017 %}
{% assign years_exp = current_year | minus: start_year %}

im phil.\
{{ years_exp }} years of software development.\
Full stack - Front-End leaning. [[resume](https://resume.philcunnell.dev/)]
