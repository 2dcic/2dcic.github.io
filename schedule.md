---

title: Schedule

---

{% assign cdate = site.date | date: "%s" | plus: 0 %}{% assign cyear = cdate | date: "%Y" | plus: 0 %}{% for location in site.locations %}{% assign cindex = forloop.index %}{% assign lindex = forloop.index | minus:1 %}{% assign tnum = 0 %}
  <h3>{{ cdate | date: "%A %-d %B %Y"}}, {{ location }}</h3>
  <div class="venue">{{ site.venues[lindex] }}</div>
  <table class="talks">{% assign cdate = cdate | plus: 86400 %}{% for slot in site.schedule %}
    {% if slot.type != "reception" or cindex == 2 %}<tr><td>{{ slot.time }}</td><td>{% if slot.type == "coffee" %}coffee{% elsif slot.type == "lunch" %}lunch break{% elsif slot.type == "reception" %}reception{% elsif slot.type == "talk" %}{% assign tnum = tnum | plus: 1 %}{% for talk in site.talks %}{% if talk.year == cyear and talk.day == cindex and talk.number == tnum %}<input id="_{{ talk.day }}_{{ talk.number }}" type="checkbox">
    <label {% if talk.title != "" %}class="drop"{% endif %} for="_{{ talk.day }}_{{ talk.number }}">{% if talk.link %}<a href="{{ talk.link }}">{% endif %}{{ talk.speaker }}{% if talk.link %}</a>{% endif%} ({{ talk.affiliation }})<br />{{ talk.title }}</label>
    <div class="abstract">{{ talk.excerpt }}</div>{% endif %}{% endfor %}{% endif %}</td></tr>{% endif %}
  {% endfor %}
    <!-- {% for talk in site.talks %}{% if talk.year == cyear and talk.day == cindex %}
    <li><input id="_{{ talk.day }}_{{ talk.number }}" type="checkbox">
    <label class="drop" for="_{{ talk.day }}_{{ talk.number }}">{% if talk.link %}<a href="{{ talk.link }}">{% endif %}{{ talk.speaker }}{% if talk.link %}</a>{% endif%} ({{ talk.affiliation }})</label>
    <div>{{ talk.title }}</div>
    </li>{% endif %}{% endfor %} -->
  </table>
{% endfor %}
