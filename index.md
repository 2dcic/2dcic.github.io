---
title: Colloqouia in Combinatorics
---

2025 sees the eighteenth year of the Colloquia in Combinatorics. Each year, we present a dozen talks covering a wide range of topics of interest to anyone working in combinatorics or related fields.

**Event organisers:** {% for item in site.data.organisers %}{% if forloop.last == true and forloop.first == false %}and {% endif %}{% if item.link %}<a href="{{ item.link }}">{% endif %}{{ item.name }}{% if item.link %}</a>{% endif %} ({{ item.affiliation }}){% if forloop.last == false %}, {% endif %}{% endfor %}


{% for item in site.data.support %}{% if forloop.first == true %}Support from {% endif %}{% if forloop.last == true and forloop.first == false %}and {% endif %}{% if item.link %}<a href="{{ item.link }}">{% endif %}{{ item.name }}{% if item.link %}</a>{% endif %}{% if forloop.last == false %}, {% endif %}{% endfor %}{% if forloop.last == true %} is gratefully acknowledged.{% endif %}
