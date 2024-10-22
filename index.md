---

title: Colloqouia in Combinatorics

---

{{ site.year }} sees the {{ site.edition }} year of the Colloquia in Combinatorics. Each year, they feature a dozen talks covering a wide range of topics of interest to those working in combinatorics or related fields.

{% for item in site.organisers %}{% if forloop.first == true %}The {{ site.year }} Colloquia are organised by {% endif %}{% if forloop.first == false and forloop.last == false or forloop.index != 2 %},{% endif %} {% if forloop.last == true and forloop.first == false %}and {% endif %}{% if item.link %}<a href="{{ item.link }}">{% endif %}{{ item.name }}{% if item.link %}</a>{% endif %} ({{ item.affiliation }}){% if forloop.last == true %}.{% endif %}{% endfor %}

{% for item in site.support %}{% if forloop.first == true %}Support from {% endif %}{% if forloop.first == false and forloop.last == false or forloop.index != 2 %}{{ forloop.index }},{% endif %} {% if forloop.last == true and forloop.first == false %}and {% endif %}{% if item.link %}<a href="{{ item.link }}">{% endif %}{{ item.name }}{% if item.link %}</a>{% endif %}{% if forloop.last == true %} is gratefully acknowledged.{% endif %}{% endfor %}
