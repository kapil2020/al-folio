---
layout: page
title: projects
permalink: /projects/
description: A growing collection of your cool projects.
nav: true
nav_order: 3
display_categories: [work, fun]
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>

<!-- Project details -->

<!-- DRUM Project -->
<div class="project-detail">
  <h2>DRUM: Dynamic Route Planning for Urban Green Mobility</h2>
  <p>A real-time web application offering sustainable, low-pollution route options based on AQI and traffic data.</p>
  <p><strong>Role:</strong> Led the development of DRUM, a route planner integrating pollution and traffic data for green travel decisions.</p>
  <p><strong>Publication:</strong> <a href="https://doi.org/10.1177/03611981251331011" target="_blank">Transportation Research Record (2025)</a></p>
</div>

<!-- TUTEM Project -->
<div class="project-detail">
  <h2>TUTEM: Technologies for Urban Transit to Enhance Mobility</h2>
  <p>ADB-funded research to improve multimodal accessibility and reduce pollutant exposure in Indian cities.</p>
  <p><strong>Institution:</strong> Indian Institute of Technology Kharagpur</p>
  <p><strong>Focus:</strong> Transit modernization, accessibility planning, and pollution mitigation strategies.</p>
</div>
