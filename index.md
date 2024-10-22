---
title: Colloqouia in Combinatorics
---

2025 sees the eighteenth year of the Colloquia in Combinatorics. Each year, we present a dozen talks covering a wide range of topics of interest to anyone working in combinatorics or related fields.

Event organisers: {% for item in site.data.organisers %}{% if forloop.last == true %}and {% endif %}{% if item.url != ""}<a href="{{ item.url }}">{% endif }{{ item.name }}</a> ({{ item.affiliation }}) {% if forloop.last == false %}, {% endif %}{% endfor %}