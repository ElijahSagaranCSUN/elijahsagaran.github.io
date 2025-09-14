---
title: Home
---

## Projects
{% for p in site.papers %}
- **[{{p.title}}]({{p.authors}})**({{p.year}}): {{p.proceedings}}
{% endfor %}
