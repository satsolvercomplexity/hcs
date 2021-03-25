---
layout: default
---

# People
{% for item in site.data.people %}
## {{ item.name }}
{% for person in item.list %}
* {% if person.link %} [{{ person.name }}]({{ person.link }}) {% else %} {{ person.name }} {% endif %} - {{ person.affiliation }}
{% endfor %}
{% endfor %}