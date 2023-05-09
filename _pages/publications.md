---
layout: page
permalink: /publications/
title: PUBLICATIONS
description: 
years: [2023, 2022, 2020, 2019]
yearp: [2100]
nav: true
nav_order: 1
---
<!-- _pages/publications.md -->
<div class="publications">

<!-- <h1>PRIPRINT</h1> -->
<!-- {%- for y in page.yearp %}
  <h2 class="year">Preprint</h2>
  {% bibliography -f preprint -q @*[year={{y}}]* %}
{% endfor %} -->

<!-- <h1>PUBLICATIONS</h1> -->
{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
