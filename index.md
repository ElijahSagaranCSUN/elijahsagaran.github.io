---
title: Home
---

## **About**
Hello, I am Elijah! I am an undergraduate researcher at California State University, Northridge. My research topic interests are the following: AI, ML, Digital Twins, and Human-Computer Interaction. I aspire to go into academia and become a researcher. 

## Contact Me
{{site.author}}

## Research Papers
<ul class="papers">
  {% assign me_norm = site.me | strip | downcase | remove: "." %}
  {% for p in site.papers %}
    <li>
      <strong>{{ p.title }}</strong> ({{ p.year }}) —
      {% for a in p.authors %}
        {% assign a_clean = a | strip %}
        {% assign a_norm  = a_clean | downcase | remove: "." %}
        {% if a_norm == me_norm %}
          <strong>{{ a_clean }}</strong>
        {% else %}
          {{ a_clean }}
        {% endif %}
        {% unless forloop.last %}, {% endunless %}
      {% endfor %}
      {{ p.proceedings }} 
    </li>
  {% endfor %}
</ul>

## Projects
<ul class="projects">
  {% assign m_norm = site.me | strip | downcase | remove: "." %}
  {% for p in site.papers %}
    <li>
      <strong>{{p.title}}</strong> {{ p.year }}) —
      {% for a in p.authors %}
        {% assign a_clean = a | strip %}
        {% assign a_norm = a_clean | downcase | remove: "." %}
        {% if a_norm = me_norm %}
          <strong>{{a_clean}}</strong>
        {% else %}
          {{ a_clean }}
        {% endif %}
        {% unless forloop.last %}, {% endunless %}
      {% endfor %}
      {{p.link}}
    </li>
</ul>

## Oral Presentations
{% for p in site.oral_presentations %}
- **[{{p.title}}]** — {{ p.event}}
{% endfor %}

## Poster Presentations
{% for p in site.poster_presentations %}
- **[{{p.title}}]** — {{p.event}}
{% endfor %}

## Skills
{% for p in site.skills %}
- Language: {{p.language}}
- Libraries: {{p.libraries}}
- Others: {{p.others}}
- Machine Learning: {{p.machine_learning}}
