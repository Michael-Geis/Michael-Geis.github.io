---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

## Scaling asymptotics for ladder sequences of spherical harmonics at caustic latitudes

#### We prove that certain 'ladder' sequences of spherical harmonics are Lagrangian distributions whose semi-classical $L^2$ mass lies over a band around the standard equator of $S^2$ bounded by latitude circles which are caustics. We derive Airy scaling asymptotics for such sequences in a shrinking neighborhood of these caustic latitudes."

*Scaling Asymptotics for Ladder Sequences of Spherical Harmonics at Caustic Latitudes, Pre-print, arXiv:2208.02770*"


{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
