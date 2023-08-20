---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

## [Scaling asymptotics for ladder sequences of spherical harmonics at caustic latitudes](https://arxiv.org/abs/2208.02770)

### We prove that certain 'ladder' sequences of spherical harmonics are Lagrangian distributions whose semi-classical $L^2$ mass lies over a band around the standard equator of $S^2$ bounded by latitude circles which are caustics. We derive Airy scaling asymptotics for such sequences in a shrinking neighborhood of these caustic latitudes.

*Scaling Asymptotics for Ladder Sequences of Spherical Harmonics at Caustic Latitudes, Pre-print, arXiv:2208.02770*"

## [Concentration of quantum integrable eigenfunctions on a convex surface of revolution](https://arxiv.org/abs/2008.12482)

### We compute weak-$*$ limits of normalized empirical measures of joint eigenfunctions of the Laplacian and the generator of the $S^1$ symmetry on a convex surface of revolution. These measures detect the relative amounts of $L^2$ mass concentration of mass of the eigenfunctions restricted to the unique $S^1$ invariant geodesic, $H$. 

*Concentration of Quantum Integrable Eigenfunctions on a Convex Surface of Revolution, arXiv: 2008.12482, submitted for review, Journal of Spectral Theory.*


{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
