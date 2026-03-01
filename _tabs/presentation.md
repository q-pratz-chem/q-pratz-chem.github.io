---
title: Talks 
order: 6  
talks:   
  - date: 2026-02-24   
    type: Talk   
    title: Neural Network-based Ansatz for Strong Correlation
    event: Hot-Topics Session at 65th Sanibel Symposium, St. Augustine, FL

  - date: 2026-02-10   
    type: Talk   
    title: Neural Network-based Variational Approach for Strong Correlation
    event: Physical Chemistry Seminar, UF
    
  - date: 2025-03-05   
    type: Poster  
    title: A Novel Approach to Strong Correlation - Geminal Wavefunctions with Doubles and Singles-like Excitations
    event: RSCPoster LinkedIn Conference (Online)
    
  - date: 2025-02-24   
    type: Poster   
    title: Novel Wavefunctions for Strong Correlation - From Geminals to Restricted Boltzmann Machine  
    event: 64th Sanibel Symposium, St. Augustine, FL
    
  - date: 2024-03-05   
    type: Poster  
    title: A Novel Approach to Strong Correlation - Geminal Wavefunctions with Doubles and Singles-like Excitations
    event: RSCPoster LinkedIn Conference (Online)

  - date: 2024-02-27   
    type: Poster   
    title: Exploring strong correlation with exotic wavefunctions 
    event: 63rd Sanibel Symposium, St. Augustine, FL

  - date: 2023-11-06   
    type: Poster   
    title: 1-reference orbital geminal Coupled Cluster wavefunctions
    event: Institute of Pure and Applied Mathematics (IPAM), UCLA

  - date: 2023-10-16   
    type: Poster   
    title: Geminal-based Approach Inspired by Coupled Cluster Formalism
    event: LatinXChem 2023 (Online)
  
  - date: 2023-02-08   
    type: Poster   
    title: Taming Strong Correlation using 1-reference Geminal Coupled Cluster Ans\"atze 
    event: SFP, Virtual Winter School on Computational Chemistry (Online)

  - date: 2023-02-13   
    type: Poster   
    title: Orbital Rotations in 1-reference Geminal Coupled Cluster   
    event: 62nd Sanibel Symposium, St. Augustine, FL
    
  - date: 2023-02-28   
    type: Poster   
    title: Orbital Rotations in 1-Reference Geminal Coupled Cluster Ans\"atze for Strong Correlation  
    event: RSCPoster Twitter Conference (Online)


  - date: 2023-01-24   
    type: Invited Talk   
    title: Developing *ab initio* Methods for Strongly Correlated Systems   
    event: Baden-Württemberg International Program (Online)

  - date: 2022-10-28   
    type: Poster   
    title: Tackling Strong Correlation with Flexible Geminal and Coupled Cluster Methods
    event: LatinXChem 2022 (Online)

  - date: 2022-06-27  
    type: Poster   
    title: Incorporating Orbital Rotations in 1-Reference Geminal Coupled Cluster   
    event: 10th Triennial Molecular Quantum Mechanics (MQM) Conference, Virginia Tech, VA

    
  - date: 2022-10-24   
    type: Talk   
    title: Ihe review of research paper on `Hardware-efficient Variational Quantum Eigensolver for Small Molecules and Quantum Magnets 
    event: Quantum Computing Course Project, UF

  - date: 2022-08-05     
    type: Talk   
    title: Exploring Chemistry of Interstellar H$_3^+$ using qiskit_nature module
    event: Quantum Computing Course Project, UF

  - date: 2022-07-12     
    type: Talk   
    title: Single Excitations in 1-Reference Geminal Coupled Cluster Wavefunctions- Taming Strong Correlation with Flexible Quasiparticles
    event: FAME Conference, Tampa, FL
  
  - date: 2022-04-19     
    type: Talk   
    title: Orbital Dynamics of Interacting Galaxies - three-body simulation
    event: Computational Physics Course
    
  - date: 2022-02-14   
    type: Poster   
    title: Single Excitations in 1-Reference Geminal Coupled Cluster Method  
    event: 61st Sanibel Symposium, St. Simons Island, GA
  
  - date: 2021-12-12    
    type: Invited Talk    
    title: On my research in Quantum Chemistry, as an interdisciplinary field of Quantum Computing, for 300+ high-school students. 
    event: Quantum Lightning Talk, QxQ The Coding School   
    link: https://youtu.be/glRSdBSNy6o   
  
  - date: 2020-05-15  
    type: Talk  
    title: Particle Swarm Optimization method combined with Gaussian to generate minimum energy structures  
    event: M.S. Thesis, IIT Kharagpur, India.  
    
  - date: 2019-07-23  
    type: Talk  
    title: Software Framework of Electronic Structure for Molecules and Solids using C++ in Valeev Group.
    event: Summer Internship, Virginia Tech, USA  
---



{% assign sorted = page.talks | sort: "date" | reverse %}
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
