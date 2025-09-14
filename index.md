---
title: Home
layout: default
---

## **About**
Hello, I am Elijah! I am an undergraduate researcher at California State University, Northridge. My research topic interests are the following: AI, ML, Digital Twins, and Human-Computer Interaction. I aspire to go into academia and become a researcher. 

## Contact Me
- **Personal Email:** {{ site.author["personal email"] }}
- **University Email:** {{ site.author["university email"] }}
- **GitHub:** {{ site.socials["GitHub"] }}
- **LinkedIn:** {{ site.socials["LinkedIn"]}}

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
      {% if p.proceedings %} — {{ p.proceedings }}{% endif %}
    </li>
  {% endfor %}
</ul>

## Projects
<ul class="projects">
  {% assign me_norm = site.me | strip | downcase | remove: "." %}
  {% for p in site.projects %}
    <li>
      <strong>{{ p.title }}</strong> ({{ p.year }}) —
      {% if p.authors %}
        {% for a in p.authors %}
          {% assign a_clean = a | strip %}
          {% assign a_norm  = a_clean | downcase | remove: "." %}
          {% if a_norm == me_norm %}<strong>{{ a_clean }}</strong>{% else %}{{ a_clean }}{% endif %}
          {% unless forloop.last %}, {% endunless %}
        {% endfor %}
        —
      {% endif %}
      {{ p.description }} {% if p.link %}(<a href="{{ p.link }}">link</a>){% endif %}
    </li>
  {% endfor %}
</ul>

## Oral Presentations
{% for p in site["oral presentations"] %}
- **{{ p.title }}** — {{ p.event }}
{% endfor %}

## Poster Presentations
{% for p in site["poster presentations"] %}
- **{{ p.title }}** — {{ p.event }}
{% endfor %}

## Skills
{% for s in site.skills %}
- **Language:** {{ s.language }}
- **Libraries:** {{ s.libraries }}
- **Others:** {{ s.others }}
- **Machine Learning:** {{ s["machine learning"] }}
{% endfor %}
