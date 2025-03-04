---

---

{% assign schedule = site.navigation | where: 'name', "Schedule" %}
{% assign speakers = site.navigation | where: 'name', "Speakers" %}
{% if schedule.size > 0 and schedule.first.link %}
  {% assign tlink = schedule.first.link %}
{% elsif speakers.size > 0 and speakers.first.link %}
  {% assign tlink = speakers.first.link %}
{% endif %}

{{ site.date | date: "%Y" }} sees the {% assign r = site.edition | modulo: 10 %}{% case r %}{% when 1 %}{{ site.edition }}st{% when 2 %}{{ site.edition }}nd{% when 3 %}{{ site.edition }}rd{% else %}{{ site.edition }}th{% endcase %} year of the Colloquia in Combinatorics. Like every year, the 2025 Colloquia feature {% if tlink %}<a href="{{ tlink | relative_url }}">{% endif %}twelve talks{% if tlink %}</a>{% endif %} covering a wide range of topics of interest to those working in combinatorics or related fields.

{% assign filtered = site.navigation | where: 'name', "Registration" %}
{% if filtered.size > 0 and filtered.first.link %}
<a href="filtered.first.link">Registration</a> for the {{ site.date | date: "%Y" }} Colloquia is now available. Standard registration is intended for participants with access to a grant or institutional travel support, Free registration for all other participants. Please register before the event.
{% endif %}

{% for item in site.organisers %}{% if forloop.first == true %}The {{ site.date | date: "%Y" }} Colloquia are organised by {% endif %}{% if forloop.first == false and forloop.last == false or forloop.index != 2 %},{% endif %} {% if forloop.last == true and forloop.first == false %}and {% endif %}{% if item.link %}<a href="{{ item.link }}">{% endif %}{{ item.name }}{% if item.link %}</a>{% endif %} ({{ item.affiliation }}){% if forloop.last == true %}.{% endif %}{% endfor %}

{% for item in site.support %}{% if forloop.first == true %}Support from {% endif %}{% if forloop.first == false and forloop.last == false or forloop.index != 2 %},{% endif %} {% if forloop.last == true and forloop.first == false %}and {% endif %}the {% if item.link %}<a href="{{ item.link }}">{% endif %}{{ item.name }}{% if item.link %}</a>{% endif %}{% if forloop.last == true %} is gratefully acknowledged.{% endif %}{% endfor %}

{% for item in site.support %}<img src="./assets/images/{{ item.logo }}" height="100" style="vertical-align:middle;padding:20px;">{% endfor %}
