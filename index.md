---

---


{{ site.date | date: "%Y" }} sees the {% assign r = site.edition | modulo: 10 %}{% case r %}{% when 1 %}{{ site.edition }}st{% when 2 %}{{ site.edition }}nd{% when 3 %}{{ site.edition }}rd{% else %}{{ site.edition }}th{% endcase %} year of the Colloquia in Combinatorics. Each year, the Colloquia feature a dozen talks covering a wide range of topics of interest to those working in combinatorics or related fields.

{% for item in site.organisers %}{% if forloop.first == true %}The {{ site.date | date: "%Y" }} Colloquia are organised by {% endif %}{% if forloop.first == false and forloop.last == false or forloop.index != 2 %},{% endif %} {% if forloop.last == true and forloop.first == false %}and {% endif %}{% if item.link %}<a href="{{ item.link }}">{% endif %}{{ item.name }}{% if item.link %}</a>{% endif %} ({{ item.affiliation }}){% if forloop.last == true %}.{% endif %}{% endfor %}

{% for item in site.support %}{% if forloop.first == true %}Support from {% endif %}{% if forloop.first == false and forloop.last == false or forloop.index != 2 %},{% endif %} {% if forloop.last == true and forloop.first == false %}and {% endif %}{% if item.link %}<a href="{{ item.link }}">{% endif %}{{ item.name }}{% if item.link %}</a>{% endif %}{% if forloop.last == true %} is gratefully acknowledged.{% endif %}{% endfor %}

{% for item in site.support %}<img src="./assets/images/{{ item.logo }}" height="100" style="vertical-align:middle;padding:20px;">{% endfor %}
