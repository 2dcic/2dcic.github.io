---

title: Schedule

---

{% assign cdate = site.date | date: "%s" | plus: 0 %}{% assign cyear = cdate | date: "%Y" | plus: 0 %}{% for location in site.locations %}
  <h3>{{ cdate | date: "%A %-d %B %Y"}}, {{ location }}</h3>
  <ul class="talks">{% assign cdate = cdate | plus: 86400 %}{% assign cindex = forloop.index %}{% for talk in site.talks %}{% if talk.year == cyear and talk.day == cindex %}
    <li><input id="_{{ talk.day }}_{{ talk.number }}" type="checkbox"> 
    <label class="drop" for="_{{ talk.day }}_{{ talk.number }}">{% if talk.link %}<a href="{{ talk.link }}">{% endif %}{{ talk.speaker }}{% if talk.link %}</a>{% endif%} ({{ talk.affiliation }})</label>
    <div>{{ talk.title }}</div>
    </li>{% endif %}{% endfor %}
  </ul>
{% endfor %}
