---
title: Home
---

# {{ site.title }}
{{ site.description }}

## Projects
{% for p in site.papers %}
- **[{{p.title}}]({{p.authors}})**({{p.year}}): {{p.proceedings}}
{% endfor %}
