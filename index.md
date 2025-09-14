---
title: Home
---

## **About**
Hello, I am Elijah! I am an undergraduate researcher at California State University, Northridge. My research topic interests are the following: AI, ML, Digital Twins, and Human-Computer Interaction. I aspire to go into academia and become a researcher. 

## Research Papers
<ul>
  {% assign me = site.me %}
  {% for p in site.papers %}
    <li>
      <strong>{{ p.title }} </strong> ({{ p.year }}) -
      {% for a in p.authors %}
      {% assign a_clean = a | strip %}
      {% if a_clean | downcase == me | downcase %}
        <strong>{{ a_clean }} </strong>
      {% else %}
        {{ a_clean }}
      {% endif %}
      {% unless forloop.last %}, {% endunless %}
    {% endfor %}
    </li>
{% endfor %}
</ul>
