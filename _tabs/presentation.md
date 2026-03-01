---
title: Talks 
order: 6
---

{% assign talks = 
"
- date: 2025-11-01
  type: Invited Talk
  title: Quantum Lightning Talk – Qubit by Qubit
  link: https://youtu.be/glRSdBSNy6o

- date: 2024-08-01
  type: Conference Talk
  title: Single Excitations in 1-Reference Geminal CC
  event: FAME Conference

- date: 2022-09-01
  type: Poster
  title: Incorporating Orbital Rotations in 1-Reference Geminal CC
  event: MQM 2022

- date: 2020
  type: Invited Talk
  title: On my research in Quantum Chemistry, as an interdisciplinary field of Quantum Computing, for 300+ high-school students. [YouTube Video](https://youtu.be/glRSdBSNy6o) 
  event: Quantum Lightning Talk, QxQ The Coding School

- date: 2020
  type: Talk
  title: Particle Swarm Optimization method combined with Gaussian to generate minimum energy structures
  event: M.S. Thesis, IIT Kharagpur, India.
  
- date: 2019
  type: Talk
  title: Software Framework of Electronic Structure for Molecules and Solids using C++ in [Valeev Group](https://valeevgroup.github.io/)
  event: Summer Internship, Virginia Tech, USA
  
" | parse_yaml %}





{% assign sorted = talks | sort: "date" | reverse %}
{% assign current_year = "" %}

<div class="timeline">

{% for item in sorted %}
  {% assign year = item.date | date: "%Y" %}

  {% if year != current_year %}
    {% assign current_year = year %}
    <h3>{{ year }}</h3>
  {% endif %}

  <p>
    <strong>[{{ item.type }}]</strong>
    {{ item.title }}
    {% if item.event %} – <em>{{ item.event }}</em>{% endif %}
    {% if item.link %} – <a href="{{ item.link }}">Link</a>{% endif %}
  </p>

{% endfor %}
</div>
